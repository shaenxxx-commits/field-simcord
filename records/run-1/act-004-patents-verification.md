# ACT-004 — независимая проверка патентов (Google Patents)

- **action_id:** ACT-004
- **run_id:** RUN-1
- **related_claim:** C-RUN1-090 (8 патентов), C-RUN1-091
- **observed_at:** 2026-10-16
- **source_id:** SRC-A004
- **source_type:** public patent database (независимый)
- **source_url:** https://patents.google.com/
- **independence_status:** независимый (Google Patents)
- **procedure:** прямой запрос карточек по номерам; для PCT — поиск через xhr/query

## Подтверждено (SUPPORTED)

| Номер (заявлен) | Google Patents ID | Название | Assignee | Inventor |
|---|---|---|---|---|
| UA138628 | UA138628U | Method of transaction of cash transfer for purpose use | ТОВ «Сімкорд» | Александр Кудь |
| UA137352 | UA137352U | Method of transaction for digital asset transfer | ТОВ «Сімкорд» | Александр Кудь |
| UA139012 | UA139012U | Digital asset transfer system | ТОВ «Сімкорд» | Александр Кудь |
| PCT/UA2017/000050 | US20190050851A1 | Method of management of property rights to assets | Simcord | Alexsandr Kud |
| PCT/UA2017/000068 | WO2020219004A1 | Method for executing a money transfer transaction for a specific purpose | Simcord | Aleksandr Kud |

5 из 8 патентов подтверждены независимо. Assignee — ТОВ «Сімкорд» / Simcord. Inventor — Кудь А. А.

## Расхождение (флаг)

**UA30256U** — в OBS-009 заявлен как «Патент на промышленный образец "Графический пользовательский интерфейс компьютерной программы iPro Marketplace", Украина, 30256, 2015».

В Google Patents UA30256U — это:
- «Ceramic mass for preparation of brick building products»
- Assignee: Национальный технический университет «Харьковский политехнический институт»
- Inventors: Рыщенко М. И., Щукина Л. П., Федоренко Е. Ю.

**Номер не соответствует. Возможные объяснения:**
1. Ошибка в нумерации на сайте Simcord (правильный номер — другой).
2. Разные типы регистрации в одной юрисдикции (промобразец может иметь отдельную нумерацию, не совпадающую с патентом на изобретение).
3. Устаревание/перерегистрация.
4. Ошибка в Google Patents.

Не разрешаю. Фиксирую расхождение.

## UNKNOWN

- **KZ30184** — патент Казахстана «Система организации процесса электронной торговли финансовыми инструментами» (заявлен Simcord, 2015). В Google Patents — 404. [НЕИЗВЕСТНО]
- **KZ4296** — патент Казахстана «Способ осуществления транзакции по передаче цифровой ценности...» (заявлен Simcord, 2019). В Google Patents — 404. [НЕИЗВЕСТНО]
- **UA30256** — расхождение (см. выше). [НЕИЗВЕСТНО], какой номер правильный.
- **Полный статус каждого патента** (действующий/просрочен/отозван) — не проверялся.

## Итог ACT-004

- **5 SUPPORTED** (C-RUN1-090 частично) — независимая цепочка построена.
- **1 расхождение** (UA30256).
- **2 UNKNOWN** (KZ).

## H1 — поддержка

ACT-004 добавляет ещё 5 подтверждённых claim к H1. Всего в Run 1 после ACT-002 и ACT-004: **10 SUPPORTED**, 1 расхождение, 3 UNKNOWN.

## NEXT STEP

Обновить meta/transitions.md (5 новых SUPPORTED). Затем ASSESS/LEARN/NEXT MOVE Run 1.
