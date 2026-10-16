# OBS-022 — TLS-сертификаты (Certificate Transparency) по трём доменам

- **observation_id:** OBS-022
- **run_id:** RUN-2
- **entity_id:** E1 (LEGAL_ENTITY), E2 (BRAND), E3 (PRODUCT Bitbon), E4 (RELATED)
- **observed_at:** 2026-10-16
- **source_id:** SRC-R2-003
- **source_type:** public Certificate Transparency (crt.sh), независимый
- **independence_status:** независимый (CT-логи — обязательные публичные реестры для всех публичных TLS-сертификатов)
- **procedure:** curl https://crt.sh/?q=%25.<domain>&output=json; извлечение уникальных имён из name_value
- **raw_files:** ~/field-simcord-raw/run2-crt-001-simcord.com.json (sha256: 9246d0fd0b33d92fc08c2428fdf9e2db0eaa6955e11be57f1d160e0009f6d6a0)
              ~/field-simcord-raw/run2-crt-002-bitbon.space.json (sha256: 4df9f83412f1d9a4326d63e21f8ffec5cbf6873b0ff26d7c4fb9fd291480aec6)
              ~/field-simcord-raw/run2-crt-003-bitbon.com.json (sha256: 903ed8491d322622b801564c2d21e349001ec4a69d90705f0ea56ebc5cfb2840)

## Правило разметки (D1)

Наблюдения — то, что зафиксировано в CT-логах. Наличие сертификата на поддомен **не означает**, что сервис сейчас работает. CT-лог хранит историю.

## simcord.com — 50 уникальных имён

### Почтовые поддомены
- mx1.simcord.com, mx2, mx3, mx4, mx5 (5 почтовых серверов)
- mail.simcord.com, mailrelay.simcord.com, autodiscover.simcord.com
- postmaster@simcord.com, hostmaster@simcord.com (в полях name_value — служебные адреса)

### Корпоративные инструменты
- **scm.simcord.com** — вероятно, Source Control (Git)
- **src.simcord.com** — likely source
- **confluence-test.simcord.com** — тестовый Confluence (Atlassian wiki)
- **vault.simcord.com** — HashiCorp Vault (секреты)
- **passman.simcord.com** — password manager
- **cas.simcord.com** — Central Authentication Service

### Инфраструктура виртуализации
- **pve-02.aecs.simcord.com, pve-03, pve-04** — Proxmox Virtual Environment (как минимум 3 сервера)
- **ncloud.simcord.com** — облачный сервис
- **wnet.simcord.com**, **igw6.simcord.com**, **www.igw6.simcord.com** — сетевые шлюзы

### Разработка
- dev.simcord.com, *.dev.simcord.com
- stg.simcord.com, www.stg.simcord.com
- testing.simcord.com, www.testing.simcord.com
- dockerdev.simcord.com, dockerhub1.simcord.com
- markup.simcord.com

### AI / чат / NPS
- **chatm.simcord.com**, **chatm-admin.simcord.com**, **chatm-web.simcord.com** — чат-система
- **chat.ai.simcord.com**, **aichat.simcord.com** — AI-чат
- **chatwood.simcord.com** — неизвестно, вероятно внутренний проект
- **nps-admin.simcord.com**, **nps-web.simcord.com** — Net Promoter Score или внутренняя система

### Продукты и проекты
- **www.ubkmarkets.simcord.com**, **test.ubkmarkets.simcord.com** — **UBK Markets** (вспомним OBS-009: патент на GUI iPro, и в новостях сайта — «5 years with UBK Markets»)
- **orpo.simcord.com**, ***.orpo.simcord.com** — неизвестно
- **rapp.simcord.com** — неизвестно
- **legalforum.simcord.com** — юридический форум
- **store.simcord.com** — магазин/стор

### Общие
- simcord.com, www.simcord.com, *.simcord.com

## bitbon.space — 8 уникальных имён

- bitbon.space, www.bitbon.space, *.bitbon.space
- **api.bitbon.space** — публичный API
- **metastudio.bitbon.space**, ***.metastudio.bitbon.space** — Meta Studio (совпадает с OBS-007.4: «Meta Studio DE»)
- **assetboxes.stg.bitbon.space** — Assetbox (совпадает с OBS-010: торговая марка Assetbox™), staging-версия
- **test.bitbon.space** — тестовая среда

## bitbon.com — 1 имя

- www.bitbon.com — только www. Домен пассивный (совпадает с OBS-021.3).

## Сводка технического следа

| Домен | Кол-во поддоменов | Характер |
|---|---|---|
| simcord.com | 50 | широкая инфраструктура: почта, разработка, AI, виртуализация, продукты |
| bitbon.space | 8 | только продуктовая инфраструктура Bitbon |
| bitbon.com | 1 | пассивный |

## Что из этого следует

1. **simcord.com — зрелая IT-инфраструктура.** 5 почтовых серверов, SCM, Confluence, Vault, Proxmox (3+ сервера), dev/stg/testing/docker среды. Это указывает на реальную технологическую активность (не только сайт).

2. **Внутренние инструменты AI.** `chat.ai`, `aichat`, `chatm` — компания работает над AI-продуктами внутри. Публично на сайте эти сервисы **не упомянуты** в OBS-007 (products-and-services). Расхождение: инфраструктура есть, публичного описания нет.

3. **UBK Markets — связанный проект.** Поддомен `ubkmarkets.simcord.com` в домене simcord.com. Это подтверждает связь E4 (RELATED). UBK Markets ранее упоминалась в новостях сайта (OBS-005: «5 years with UBK Markets»). Также есть патент на GUI iPro, но он не совпал по номеру (OBS-009, ACT-004).

4. **`pve-02/03/04`** — три сервера Proxmox. Это указывает на определённый масштаб: собственные (или арендуемые) серверы, не только облачный хостинг.

5. **`assetboxes.stg.bitbon.space`** — подтверждает продукт Assetbox (TM в OBS-010) как реально существующую техническую единицу с staging-окружением.

6. **`metastudio.bitbon.space`** — подтверждает продукт Meta Studio DE (OBS-007.4) как реально существующий.

7. **`vault`, `passman`, `cas`** — указывает на зрелую инфраструктурную практику (управление секретами, аутентификация). Это не маркетинговый след, а реальная техническая культура.

## UNKNOWN

- Активны ли все 50 поддоменов сейчас — [НЕИЗВЕСТНО] (CT-лог историчен).
- Даты первых/последних сертификатов по каждому поддомену — [НЕИЗВЕСТНО] (требует более детального парсинга).
- Что такое `orpo`, `rapp`, `chatwood`, `igw6` — [НЕИЗВЕСТНО].
- Публичный ли репозиторий в `scm.simcord.com` или это внутренний — [НЕИЗВЕСТНО].
- Связь UBK Markets с Simcord — [НЕИЗВЕСТНО] на уровне юрлица (требует проверки).

## NEXT STEP

OBS-023: исторический Wayback по simcord.com за 2008–2011 — что было на домене до регистрации юрлица. Закроет вопрос OBS-020.1.
