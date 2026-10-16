# OBS-020 — WHOIS/RDAP по доменам simcord.com, bitbon.space, bitbon.com

- **observation_id:** OBS-020
- **run_id:** RUN-2
- **entity_id:** E1 (LEGAL_ENTITY), E2 (BRAND), E3 (PRODUCT Bitbon)
- **observed_at:** 2026-10-16
- **source_id:** SRC-R2-001
- **source_type:** public registry (RDAP), независимый
- **independence_status:** независимый (публичный протокол регистрации доменов)
- **procedure:** curl https://rdap.org/domain/<domain>; сохранение JSON; извлечение полей
- **raw_files:** ~/field-simcord-raw/run2-whois-001-simcord.com.json (sha256: 51e9691424e0e8f20e955a6d59a3c330e7d87a91cab8c01bf118a0cb249f135e)
              ~/field-simcord-raw/run2-whois-002-bitbon.space.json (sha256: 519934e132effd36289ef4c123dbf21eb04e408b562f794023019f6cd2302264)
              ~/field-simcord-raw/run2-whois-003-bitbon.com.json (sha256: ec4af1681907a841e23897568020c68363acbe0e38d760954648089f027f5704)

## Правило разметки (D1)

Наблюдения — то, что зафиксировано в публичном реестре доменов. Принадлежность домена юрлицу Simcord **не устанавливается** автоматически: регистрация домена ≠ владение через юрлицо (может быть приватное лицо, реселлер, другое юрлицо).

## Наблюдения

**OBS-020.1 — simcord.com**
- Registration: **2008-08-28**
- Expiration: 2027-08-28
- Last changed: 2026-07-06
- NS: AMANDA.NS.CLOUDFLARE.COM, BART.NS.CLOUDFLARE.COM
- Registrar: скрыт (ID 1112)
- Тип: OBSERVATION. Статус: SUPPORTED (реестр).
**Расхождение:** домен зарегистрирован в **2008**, тогда как ТОВ «СІМКОРД» зарегистрировано **27.04.2011** (OBS-015.1). Домен старше юрлица на ~2,5 года. Либо домен был куплен позже у предыдущего владельца, либо зарегистрирован на другое лицо. Требует проверки через Wayback за 2008–2011.

**OBS-020.2 — bitbon.space**
- Registration: **2016-07-09**
- Expiration: 2027-07-09
- Last changed: 2026-06-07
- NS: amanda.ns.cloudflare.com, bart.ns.cloudflare.com
- Registrar: ID 303
- Тип: OBSERVATION. Статус: SUPPORTED (реестр).
- **Совпадение NS с simcord.com** (оба — Cloudflare amanda/bart). Косвенно указывает на общее управление DNS.

**OBS-020.3 — bitbon.com**
- Registration: **2011-04-15**
- Expiration: 2027-04-15
- Last changed: 2026-03-16
- NS: DNS1.REGISTRAR-SERVERS.COM, DNS2.REGISTRAR-SERVERS.COM
- Registrar: ID 1068
- Тип: OBSERVATION. Статус: SUPPORTED (реестр).
**Расхождение:** NS **не Cloudflare** — отличаются от simcord.com и bitbon.space. Домен управляется через другой DNS-провайдер. Домен зарегистрирован **2011-04-15**, на 12 дней **до** регистрации юрлица ТОВ «СІМКОРД» (2011-04-27).

## Сводка

| Домен | Регистрация | NS | Registrar |
|---|---|---|---|
| simcord.com | 2008-08-28 | Cloudflare | скрыт (1112) |
| bitbon.space | 2016-07-09 | Cloudflare | 303 |
| bitbon.com | 2011-04-15 | registrar-servers.com | 1068 |

## Что из этого следует

1. **Домен simcord.com старше юрлица на 2,5 года.** Если компания его не регистрировала в 2008 (её ещё не существовало), это либо вторичная покупка, либо регистрация на другое лицо. Требует проверки по Wayback.
2. **Домен bitbon.com зарегистрирован за 12 дней до регистрации юрлица** — близко по времени, но не совпадает. Не редкость для подготовки к запуску, но фиксируется.
3. **bitbon.com — вне Cloudflare.** Отделён от двух других доменов по управлению DNS. Это может означать: другой владелец, другой сервис, или другая политика управления. Требует проверки.
4. **simcord.com и bitbon.space на одном DNS-провайдере (Cloudflare, те же NS).** Косвенно указывает на единое управление. Но при использовании Cloudflare разными владельцами NS могут совпадать — это не доказательство.

## UNKNOWN

- Владелец каждого домена (Registrant) — скрыт через privacy-сервисы.
- Принадлежит ли simcord.com ТОВ «СІМКОРД» формально или это другое лицо — [НЕИЗВЕСТНО].
- Кто владеет bitbon.com (Simcord или другая структура) — [НЕИЗВЕСТНО].
- История домена simcord.com 2008–2011 — [НЕИЗВЕСТНО], требует Wayback.
- Связь bitbon.space с Simcord — [НЕИЗВЕСТНО], требует проверки содержимого.

## NEXT STEP

OBS-021: DNS-проверка (A, MX, TXT-записи) для трёх доменов через публичный Google DNS API. Затем — TLS-сертификаты через crt.sh. Затем — Wayback по simcord.com за 2008–2011.
