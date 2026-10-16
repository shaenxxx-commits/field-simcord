# OBS-024 — OpenCorporates: поиск «Simcord» в юрисдикциях

- **observation_id:** OBS-024
- **run_id:** RUN-2
- **entity_id:** E1 (LEGAL_ENTITY), E4 (RELATED)
- **observed_at:** 2026-10-16
- **source_id:** SRC-R2-005
- **source_type:** public corporate registry aggregator (OpenCorporates), независимый
- **independence_status:** независимый
- **procedure:** поиск по запросу «Simcord» на opencorporates.com; открытие карточки латвийского юрлица
- **raw_files:** ~/field-simcord-raw/run2-opencorporates-search-simcord.html (sha256: 88b2026d477e420022495db3e23e66c018023829d6a7d176665203fea85aa0e1)
              ~/field-simcord-raw/run2-opencorporates-lv-40103781754.html (sha256: e4d956041d3f9c920d234344154eda2a05dec3b6680a99161a0de066eb5b3960)

## Правило разметки (D1)

Наблюдения — то, что зафиксировано в OpenCorporates. Полные данные (дата регистрации, dissolution) скрыты за платным доступом.

## Наблюдения

**OBS-024.1 — результаты поиска «Simcord»**
Поиск по OpenCorporates вернул три юрлица:
1. **ACN 003 059 407 LIMITED** (Австралия) — не связано (старая регистрация, 1987).
2. **SIA «SIMCORD INFORMATION SERVICES»** (Латвия, № 40103781754) — совпадение по имени.
3. **SIMCORD ADVANCED MARKETING SOLUTIONS LLP** (Великобритания, № OC389221) — вероятно, не связано (маркетинг, отдельное LLP).
Тип: OBSERVATION. Статус: SUPPORTED.

**OBS-024.2 — латвийское юрлицо SIA «SIMCORD INFORMATION SERVICES»**
- Регистрационный номер: **40103781754**
- Форма: Sabiedrība ar ierobežotu atbildību (ООО, Латвия)
- Адрес: «Auseika» - 2, Auseika, Nīcgales pag., Augšdaugavas nov., Латвия
- Дата регистрации: **скрыта платным доступом**
- Dissolution date: скрыта платным доступом
- Источник данных: латвийский реестр (UR)
Тип: OBSERVATION. Статус: SUPPORTED.

## Сопоставление

**Simcord Information Service уже встречался ранее:**
- OBS-002.1 (development-strategy, ua): «Інтерв'ю з Олександром Кудем для Simcord Information Service, датоване 7 березня 2019 року» (упоминалось в новостной рубрике; текст OBS-002 не сохранял конкретно это, но в news sitemap есть публикации с этим именем — OBS: см. /news/interview-with-alexander-kud-for-simcord-information-service и /news/interview-with-alexander-kud-for-simcord-information-service-dated-march-7-2019).

**Соответствие:** латвийское юрлицо «Simcord Information Services» совпадает по имени с упоминанием на сайте Simcord. Это **третий региональный след** после Украины (ТОВ «СІМКОРД») и упоминаний о «региональных операторах Bitbon» (OBS-011.2, OBS-013.3).

## Что из этого следует

1. **Есть латвийское юрлицо с именем Simcord.** Это не украинская Simcord и не американская «Simcord Inc» (2010). Отдельная организация в ЕС.
2. **Связь с ТОВ «СІМКОРД»** — [НЕИЗВЕСТНО]. Совпадение имени недостаточно. Может быть: дочерняя структура, партнёр, оператор Bitbon, независимое юрлицо с тем же брендом.
3. **Дат регистрации нет.** Платная стена OpenCorporates. Требует отдельного источника (латвийский UR — публичный).
4. **Австралийский и британский следы** выглядят не связанными. Но это предположение, не проверено.

## UNKNOWN

- Дата регистрации латвийского SIA — [НЕИЗВЕСТНО].
- Активно ли оно сейчас (dissolution date скрыт) — [НЕИЗВЕСТНО].
- Связь с ТОВ «СІМКОРД» — [НЕИЗВЕСТНО].
- Есть ли ещё юрлица «Simcord» в других юрисдикциях (Кипр, США, Китай) — [НЕИЗВЕСТНО]. Поиск дал только три результата, но OpenCorporates не полный.
- Кто такой «Simcord Inc» (2010, OBS-023) — [НЕИЗВЕСТНО]. Может быть связано с любым из трёх или ни с кем.

## NEXT STEP

ACT-005: проверка латвийского SIA через публичный реестр Латвии (UR — info.ur.gov.lv) — даст даты, статус, руководителя.
