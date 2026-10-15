# OBS-014 — en/innovative-solutions

- **observation_id:** OBS-014
- **run_id:** RUN-1
- **entity_id:** E2 (BRAND), E4 (RELATED: все перечисленные услуги)
- **observed_at:** 2026-10-16
- **archive_timestamp:** 2026-01-18 00:52:21 (Wayback)
- **published_at:** [НЕИЗВЕСТНО]
- **source_id:** SRC-014
- **source_type:** corporate
- **source_url:** https://www.simcord.com/en/innovative-solutions
- **source_url_actual:** http://web.archive.org/web/20260118005221/https://www.simcord.com/en/innovative-solutions
- **raw_file:** ~/field-simcord-raw/run1-014-innovative-solutions-en.html
- **raw_size:** 1217298
- **raw_sha256:** ccba9a86059f40e3e03e95cca799c668d6e27fe1bdea4670aee6192ba24dccd3
- **independence_status:** зависимый (самоописание компании)
- **language:** en
- **note:** ua и ru версии в Wayback отсутствуют для этого раздела.

## Правило разметки (D1)

Все наблюдения — **факты публикации**. Истинность содержания не устанавливается.

## Наблюдения

**OBS-014.1 — claim_id C-RUN1-140** (сводный перечень услуг)
Компания публикует 14 направлений инновационных решений:
1. Blockchain Protocols and Consensus Algorithms (разработка протоколов, консенсус-алгоритмов, смарт-контрактов)
2. Building Analytical Stacks for Processing Big Data (R, Python, NoSQL)
3. Market Liquidity Aggregation Systems (Capital Management) — работа с банками, FX-брокерами, крипто-биржами, FIX-протоколы
4. Developing Tools for Brokerage Services (деривативы, акции, облигации)
5. Hardware and Software Complexes for Trading on Global Financial Markets (trading server admin, аренда ПО)
6. Website and Web App Development
7. Mobile App Development (Android, iOS)
8. Organization of Information Security Systems (аудит, политика ИБ, анализ уязвимостей)
9. Legal Advice and Support (в т.ч. «Obtaining licenses in financial and technical fields in different countries», «Intellectual property protection»)
10. Consulting Services in Digital Technologies on Global Financial Markets
11. Comprehensive Solutions for Customer and Technical Support (AMS-система)
12. Load Testing, Modeling of Efficiency and Performance of Apps
13. News Flow and Data Aggregation
14. APIs for Developers
Тип: OBSERVATION.
Статус: [ФАКТ публикации].

**OBS-014.2 — claim_id C-RUN1-141** (паттерн: доля блокчейн-услуг)
Из 14 направлений только **1 (#1)** прямо относится к блокчейну. Остальные 13 — финансовые, IT-разработка, ИБ, юридические, аналитика, тестирование.
Тип: INTERPRETATION (наблюдение о соотношении).
Статус: [ФАКТ публикации] (сам список — факт). Соотношение — интерпретация на основе опубликованного.
**Значимость:** это уже **третий случай** подобного расхождения:
- OBS-000 (meta сайта): «Створення програмних рішень із використанням технологій розподіленого реєстру».
- OBS-007 (products-and-services): iPro, LMS, iPA, SSO — вне Bitbon.
- OBS-014: 1 из 14 направлений — блокчейн.

Все три согласованно указывают: заявленное позиционирование «блокчейн-компания» **не покрывает** фактического перечня публично предлагаемых услуг. Большая часть — финансовые и IT-услуги общего профиля.
Это **не обвинение** и не правовая квалификация. Это фиксируемое несоответствие между узким самоописанием и широким портфелем.

**OBS-014.3 — claim_id C-RUN1-142** (услуга «получение лицензий»)
Выдержка: «Legal Advice and Support... Obtaining licenses in financial and technical fields in different countries.»
Тип: RESULT.
Статус: [ФАКТ публикации].
**Значимость:** компания публично предлагает **получение лицензий в финансовой сфере в разных странах**. Это отдельный чувствительный сюжет. Само по себе — обычная консалтинговая услуга, но контекст (Bitbon заявлен как финансовая экосистема) усиливает значимость.

**OBS-014.4 — claim_id C-RUN1-143** (Big Data и биометрия)
Выдержка (из #11): «Analyzing biometric data.»
Тип: OBSERVATION.
Статус: [ФАКТ публикации]. AMS-система собирает и анализирует биометрические данные клиентов. Наблюдение о характере данных, не оценка.

**OBS-014.5 — claim_id C-RUN1-144** (12 направлений vs 14 услуг)
В OBS-012 (ua/additional-information) компания заявляет **12 направлений деятельности**. В OBS-014 (en/innovative-solutions) — **14 направлений инновационных решений**. Списки пересекаются, но не совпадают. Это ещё одна аномалия презентации: разные страницы сайта дают разные «полные» перечни одной и той же деятельности.
Тип: OBSERVATION (структурная аномалия).
Статус: [ФАКТ публикации].

## Сводная карта Run 1 (OBSERVE) — состояние

14 наблюдений (OBS-000 — meta-уровень, OBS-001..014 — страницы/документы). Источники — только официальный сайт + Wayback.

Наблюдаемые паттерны:
- **Расхождение позиционирования и портфеля** (OBS-007, OBS-014, OBS-000).
- **Отсутствие юридической конкретики** там, где она ожидается (OBS-011 legal-information без реквизитов и лицензий).
- **Разные цифры для одного объекта**: 12 направлений vs 14 решений (OBS-012 vs OBS-014).
- **Аномалии презентации**: смешение статусов, дублирование текста, повторяющиеся номера (OBS-010, OBS-012).
- **Проверяемые claim**: ISO UA231316 (OBS-006, ACT-001 UNKNOWN), 8 патентов (OBS-009), ~25 ТМ (OBS-010).
- **Институциональная роль**: операторы Bitbon, включая «государства» (OBS-011, OBS-013).

## UNKNOWN

- Все перечисленные выше [НЕИЗВЕСТНО] остаются.
- Пересечение официального «ядра» и наблюдаемых противоречий будет оценено в Run 1 SYNTHESIS.

## NEXT STEP

Run 1 SYNTHESIS (records/000-SYNTHESIS-run1.md): сборка всех 14 наблюдений, выделение подтверждённых/неподтверждённых claim, паттернов, ключевых неизвестных. Затем — серия ACT по внешним реестрам (ЕГРПОУ, WIPO Madrid Monitor, PATENTSCOPE, Bureau Veritas).
