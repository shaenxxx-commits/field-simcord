# OBS-030 — Запуск Integrated ECN (2017) и «группа компаний Simcord»

- **observation_id:** OBS-030
- **run_id:** RUN-3
- **entity_id:** E2 (BRAND), E4 (RELATED: Integrated ECN)
- **observed_at:** 2026-10-16
- **published_at:** событие — 13.03.2017; дата публикации [НЕИЗВЕСТНО]
- **source_id:** SRC-R3-005
- **source_type:** corporate (news)
- **independence_status:** зависимый (самоописание компании)
- **source_url:** https://www.simcord.com/ua/news/expansion-of-simcord-holding-launch-of-integrated-ecn-company
- **raw_file:** ~/field-simcord-raw/run3-005-integrated-ecn-2017.html
- **raw_size:** 1556868
- **raw_sha256:** 8073ca5a5fb9cf5cc6e0560c81c1dd5345200ee18366c05416942d3f993ba58e
- **language:** ua

## Правило разметки (D1)

Все наблюдения — факты публикации. Истинность содержания не устанавливается.

## Наблюдения

**OBS-030.1 — «група компаній Simcord»** — claim_id C-RUN3-040
Выдержка: «Integrated ECN — головного дистриб'ютора програмно-технічних і наукових розробок **групи компаній Simcord**».
Тип: OBSERVATION. Статус: [ФАКТ публикации].
Значимость: в 2017 компания позиционирует себя как **группа компаний**, а не единственное юрлицо. Integrated ECN — часть группы.

**OBS-030.2 — запуск Integrated ECN** — claim_id C-RUN3-041
Выдержка: «13 березня 2017 року відбувся запуск компанії Integrated ECN — головного дистриб'ютора програмно-технічних і наукових розробок групи компаній Simcord».
Тип: RESULT. Статус: [ФАКТ публикации].

**OBS-030.3 — назначение Integrated ECN** — claim_id C-RUN3-042
Выдержка: «Integrated ECN — основний елемент B2B-системи у сфері надання брокерських послуг для торгівлі на фінансових ринках».
Тип: OBSERVATION. Статус: [ФАКТ публикации].
Значимость: подтверждает, что трейдинг-направление (iPro, iPA, LMS из OBS-007) развивалось через отдельную структуру Integrated ECN.

**OBS-030.4 — iPA-сервис** — claim_id C-RUN3-043
Выдержка: «iPA-Сервіс (Original, Processed & Volume), в основі якого лежить технологія iPA (Intelligent Processing Algorithms), — головний компонент iPA-Системи».
Тип: OBSERVATION. Статус: [ФАКТ публикации].
Значимость: iPA — не отдельный сервис Bitbon, а разработка Integrated ECN.

## Что из этого следует

1. **«Група компаній Simcord» — уже в 2017.** Группа шире, чем ТОВ «СІМКОРД». Понятие E4 (RELATED) подтверждено как минимум одной публично названной структурой (Integrated ECN).
2. **Разделение направлений.** Bitbon-направление (через Simcord) отделено от трейдинг-направления (через Integrated ECN). Это объясняет, почему iPro, iPA, LMS в OBS-007 выглядят «вне Bitbon» — они относятся к другой компании группы.
3. **Integrated ECN — не «Simcord LLC».** Это отдельная структура внутри группы. Не путать.
4. **Хронология:** Integrated ECN запущен 13.03.2017 — **за год до** первого цикла ISO-сертификации ТОВ (06.04.2018) и **за два года до** первого blockchain-репозитория (декабрь 2019).

## UNKNOWN

- Юридический статус Integrated ECN (где зарегистрирован, кто владелец) — [НЕИЗВЕСТНО].
- Связь Integrated ECN с ТОВ «СІМКОРД» на уровне владельцев — [НЕИЗВЕСТНО].
- Что ещё входит в «групу компаній Simcord» — [НЕИЗВЕСТНО], требует поиска.
- Работает ли Integrated ECN сейчас — [НЕИЗВЕСТНО].

## NEXT STEP

OBS-031: official-visit-member-board-luxembourg-ukraine-chamber-commerce-company-office — Люксембург.
