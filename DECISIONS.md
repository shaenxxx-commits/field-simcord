# DECISIONS.md
Журнал решений проекта field-simcord.
Режим: append-only. Статусы не редактируются в существующих записях — переход статуса оформляется новой записью со ссылкой на предыдущую.

Формат записи:

### D-YYYYMMDD-XX — Краткое название
- **Статус:** proposed | accepted | rejected | superseded
- **Дата:** YYYY-MM-DD
- **Утверждающий:** [Архитектор / роль / агент]
- **Контекст:**
- **Решение:**
- **Основание:**
- **Последствия:**
- **Условие пересмотра:**
- **Связанные документы / записи:**
- **Заменяет (если superseded):** D-YYYYMMDD-XX

---

### D-000000-00 — Initial setup field-simcord
- **Статус:** accepted
- **Дата:** 2026-10-15
- **Утверждающий:** Архитектор
- **Контекст:** Инициализация полевого проекта field-simcord по калиброванному каркасу KARCAS-DDA v1.1 (pilot), по образцу ENVOY.
- **Решение:** Развернуть структуру ~/field-simcord/ с минимальным ядром (README, CURRENT_STATE, DECISIONS, INVARIANTS) и библиотекой под полевую работу (00_ENTRY, docs/VISION, docs/METHOD, docs/KNOWLEDGE_STATES, meta/agent-rules, meta/handoff-protocol, meta/handoff-current, meta/transitions, meta/open-questions, PROVENANCE, records/, ARCHIVE/). Предмет исследования — компания Simcord (ТОВ «СІМКОРД», код 37657823, Украина, продукт Bitbon), вопрос: что представляет собой Simcord по публичным следам: структура, деятельность, соответствие заявленному позиционированию.
- **Основание:** Калиброванный каркас KARCAS-DDA v1.1; поручение Архитектора от 2026-10-15.
- **Последствия:** Все дальнейшие изменения инвариантов и границ требуют accepted-решений. Первичные записи — append-only.
- **Условие пересмотра:** Устойчивые проблемы при применении каркаса в полевом режиме.
- **Связанные документы:** README.md, INVARIANTS.md, CURRENT_STATE.md, docs/VISION.md, docs/METHOD.md.

---
