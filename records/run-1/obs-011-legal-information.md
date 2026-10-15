# OBS-011 — en/legal-information

- **observation_id:** OBS-011
- **run_id:** RUN-1
- **entity_id:** E1 (LEGAL_ENTITY), E2 (BRAND)
- **observed_at:** 2026-10-16
- **archive_timestamp:** 2026-01-21 21:40:05 (Wayback)
- **published_at:** [НЕИЗВЕСТНО]
- **source_id:** SRC-011
- **source_type:** corporate
- **source_url:** https://www.simcord.com/en/legal-information
- **source_url_actual:** http://web.archive.org/web/20260121214005/https://www.simcord.com/en/legal-information
- **raw_file:** ~/field-simcord-raw/run1-011-legal-information-en.html
- **raw_size:** 1207230
- **raw_sha256:** e2ff548cdb6a6386111d2d83a0cbfd635626cb7c36c95cf5a8237b97bc5db01e
- **independence_status:** зависимый (самоописание компании)
- **language:** en
- **note:** ua и ru версии в Wayback отсутствуют. Взята en.

## Правило разметки (D1)

Все наблюдения — **факты публикации**. Истинность содержания не устанавливается.

## Наблюдения

**OBS-011.1 — claim_id C-RUN1-110**
Выдержка: «Our Company strictly and responsibly observes all the rules of financial activity, providing its Customers and Partners with a reliable foundation for their business activities. In our activities, we follow the norms of international law covering all legal aspects.»
Тип: INTERPRETATION (общее заявление о соблюдении норм).
Статус: [ФАКТ публикации]. Истинность — [НЕИЗВЕСТНО].
Замечание: формулировка о соблюдении «всех правил финансовой деятельности» — сильное утверждение, но не подкреплено ссылками ни на конкретные нормы, ни на регулятора, ни на лицензии.

**OBS-011.2 — claim_id C-RUN1-111**
Выдержка: «One of the key priorities for Simcord is the development and maintenance of the economic model of the Bitbon System Social Network. The legal mechanisms for its development comply with the norms of international law and the legislation of the countries in which the regional operators of the Bitbon System carry out their activities.»
Тип: RESULT.
Статус: [ФАКТ публикации].
**Значимость:** здесь впервые прямо упомянуты **региональные операторы Bitbon** («regional operators of the Bitbon System»), которые осуществляют деятельность в разных странах. Ранее (OBS-004.4, OBS-002) упоминались «развитие производственных офисов», но не «региональные операторы». Это E4-сущность (RELATED).

**OBS-011.3 — claim_id C-RUN1-112**
Выдержка: «The protection of the Company's intellectual property rights is also an important priority.»
Тип: OBSERVATION (общее).
Статус: [ФАКТ публикации].

**OBS-011.4 — claim_id C-RUN1-113** (аномалия страницы)
Наблюдение: страница называется **«Legal Information»**, но **не содержит**:
- юридического адреса компании (кроме подвала с кодом 37657823);
- регистрационных данных (номер ЕГРПОУ, дата регистрации);
- лицензий (для финансовой деятельности в Украине);
- ссылок на регулятора или реестр;
- конкретных норм и юрисдикций, на которые ссылается;
- шаблона договоров с пользователями;
- политики конфиденциальности (возможно, есть в отдельной ссылке).

Это **несоответствие названия раздела и его содержания**. «Юридическая информация» фактически содержит общие декларации о соблюдении норм.
Тип: OBSERVATION (структура сайта).
Статус: [ФАКТ публикации].
**Значимость:** для полевого исследования это ключевой пробел. Именно здесь должны были быть юридические реквизиты, но их нет. Проверка юридической идентичности возможна только через внешний реестр (ЕГРПОУ) — что и станет отдельным шагом ACT.

**OBS-011.5 — claim_id C-RUN1-114**
Выдержка: «For all your questions regarding the Company's products, you can contact our specialists using the feedback form.»
Тип: OBSERVATION (указан канал связи).
Статус: [ФАКТ публикации]. Это форма обратной связи, не юридический контакт.

**OBS-011.6 — claim_id C-RUN1-115** (единственный юридический реквизит)
Выдержка: «Simcord LLC. Technologies. Ukraine. (Company ID code 37657823)» — в подвале.
Тип: OBSERVATION.
Статус: [ФАКТ публикации]. Это тот же код, что и в PDF сертификата (OBS-006), и в других местах. Полное юрлицо здесь указано как «Simcord LLC», что несколько не соответствует «ТОВ «СІМКОРД»» (OBS-006.1) — форма записи разная, но код совпадает.

## UNKNOWN

- Юридический адрес компании (на момент снимка) — [НЕИЗВЕСТНО] на этой странице, но есть в PDF сертификата (OBS-006): вул. Отакара Яроша, 18, м. Харків, 61045.
- Статус юрлица в ЕГРПОУ (активно/приостановлено/прекращено) — [НЕИЗВЕСТНО] без проверки реестра.
- Лицензии и разрешения для финансовой деятельности — [НЕИЗВЕСТНО].
- Что за «региональные операторы Bitbon» — [НЕИЗВЕСТНО] (отдельная линия исследования, Run 2+).
- Есть ли отдельная политика конфиденциальности / пользовательское соглашение — [НЕИЗВЕСТНО].

## NEXT STEP

OBS-012: additional-information (ua). Затем cooperation (ua), затем innovative-solutions (en). После этого — Run 1 SYNTHESIS и выход на ACT по реестрам (ЕГРПОУ, WIPO, Bureau Veritas).
