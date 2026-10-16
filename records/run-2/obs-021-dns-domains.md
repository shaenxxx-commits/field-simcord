# OBS-021 — DNS-записи по трём доменам

- **observation_id:** OBS-021
- **run_id:** RUN-2
- **entity_id:** E1 (LEGAL_ENTITY), E2 (BRAND), E3 (PRODUCT Bitbon)
- **observed_at:** 2026-10-16
- **source_id:** SRC-R2-002
- **source_type:** public DNS (Google DNS API), независимый
- **independence_status:** независимый (публичный DNS)
- **procedure:** curl https://dns.google/resolve?name=<domain>&type=<A|MX|TXT|NS>; сохранение JSON
- **raw_files:** ~/field-simcord-raw/run2-dns-<domain>-<type>.json (12 файлов; sha256 в raw-каталоге)

## Правило разметки (D1)

Наблюдения — то, что зафиксировано в публичном DNS. Связь домена с юрлицом Simcord **не устанавливается** автоматически.

## Наблюдения

**OBS-021.1 — simcord.com**
- **A:** 104.21.74.196, 172.67.206.53 — **Cloudflare** (диапазон 104.21/172.67).
- **MX:** `15 mx1.simcord.com.` — собственный почтовый сервер в домене simcord.com. Это указывает на активное управление почтой.
- **NS:** amanda/bart.ns.cloudflare.com.
- **TXT:**
  - `google-site-verification=gM9MeagyM_F0Rf7PM-3oad2itPt8deH5AS56A8fJ0kg`
  - `v=spf1 +mx -all`
  - `facebook-domain-verification=5v9bwls503fnaujt72x9uj1odnak9b`
- Тип: OBSERVATION. Статус: SUPPORTED.

**OBS-021.2 — bitbon.space** (ключевые расхождения)
- **A:** 104.25.207.6, 172.67.64.167, 104.25.206.6 — Cloudflare.
- **MX:** `0 mx.services.` — **внешний сервис**, не собственный почтовый сервер. Кто такой `mx.services` — [НЕИЗВЕСТНО].
- **NS:** amanda/bart.ns.cloudflare.com (совпадает с simcord.com).
- **TXT:**
  - `google-site-verification=2bKCmTeJ8pXnFWs_jc344l57SBotW6p_LmiFBWje8og`
  - `facebook-domain-verification=reyb2kbeu5th1x338r7lp62vwrsasu`
  - **`mailru-verification: 34daeaff555d505e`** — верификация Mail.ru. Mail.ru — российский сервис. Для украинской компании в 2026 это **аномалия**, требующая фиксации.
  - **`v=spf1 include:_spf.ukraine.com.ua include:spf.selzy.com -all`** — два сторонних почтовых провайдера: `ukraine.com.ua` (украинский хостинг) и `selzy.com` (украинский email-маркетинг).
- Тип: OBSERVATION. Статус: SUPPORTED.

**OBS-021.3 — bitbon.com** (пассивный домен)
- **A:** 162.255.119.54 — **не Cloudflare**. Это IP-диапазон Namecheap (registrar-servers.com).
- **MX:** пусто.
- **NS:** dns1/dns2.registrar-servers.com — **дефолтные NS Namecheap**.
- **TXT:** пусто.
- Тип: OBSERVATION. Статус: SUPPORTED.
**Следствие:** домен bitbon.com **не используется активно**. Ни почты, ни TXT-верификаций, ни приложения. Стандартная парковка на Namecheap.

## Сводная карта

| Домен | A | MX | NS | Особенности |
|---|---|---|---|---|
| simcord.com | Cloudflare | собственный (mx1.simcord.com) | Cloudflare | активен, собственная почта |
| bitbon.space | Cloudflare | mx.services (внешний) | Cloudflare | активен, + **mailru-verification** |
| bitbon.com | Namecheap парковка | нет | Namecheap дефолт | **не используется** |

## Что из этого следует

1. **simcord.com — основной актив.** Собственный MX, Google и Facebook верификации, SPF `+mx -all` (собственная почта). Управляется компанией.
2. **bitbon.space — рабочий, но с аномалиями.**
   - MX через внешний сервис `mx.services` (не собственная инфраструктура).
   - **Наличие `mailru-verification`** при отсутствии других российских следов. Это **единственная** связка с РФ-сервисом в DNS. Требует внимания: могла быть оставлена случайно, могла быть от прежнего владельца, может быть действующей. Не интерпретирую — фиксирую.
   - SPF через **два разных украинских провайдера** — mail через `ukraine.com.ua`, маркетинг через `selzy.com`. То есть **компания не пользуется собственной почтой для bitbon.space** (в отличие от simcord.com).
3. **bitbon.com — не работает.** Зарегистрирован в 2011, но сейчас — парковка. Продукт Bitbon на этом домене не размещён. На официальном сайте упоминается `Bitbon.space` (OBS-001.2), не `bitbon.com`.
4. **MX simcord.com = mx1.simcord.com** — единственная техническая точка, которая прямо указывает на самоподдерживаемую инфраструктуру компании.

## UNKNOWN

- Что за сервис `mx.services` (кто оператор, в какой юрисдикции) — [НЕИЗВЕСТНО].
- Активна ли mailru-verification сейчас (верификация в DNS не означает использования) — [НЕИЗВЕСТНО].
- `ukraine.com.ua` и `selzy.com` — связаны ли они с Simcord или используются как общие сервисы — [НЕИЗВЕСТНО].
- Почему bitbon.com не развивается, хотя зарегистрирован раньше bitbon.space (2011 vs 2016) — [НЕИЗВЕСТНО].
- Кто физически держит инфраструктуру Cloudflare — Simcord или подрядчик — [НЕИЗВЕСТНО].

## NEXT STEP

OBS-022: TLS-сертификаты через crt.sh по трём доменам. Это даст список поддоменов и историю сертификатов.
