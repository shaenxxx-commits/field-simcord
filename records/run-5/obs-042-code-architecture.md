# OBS-042 — Архитектура кода Bitbon: форк Geth + zk-SNARK + proof-of-concept консенсус

- **observation_id:** OBS-042
- **run_id:** RUN-5
- **entity_id:** E3 (PRODUCT Bitbon)
- **observed_at:** 2026-10-18
- **source_id:** SRC-R5-001
- **source_type:** public source code (GitHub), независимый
- **independence_status:** независимый (публичный исходный код)
- **source_url:** https://github.com/simcord-llc/bitbon-system-blockchain
- **procedure:** git clone --depth 1; анализ структуры; чтение go.mod, zksnark/zksnark.go, consensus/quorum/quorum.go, bitbon/contracts/, bitbon/transfer/
- **note:** клон локальный (50 МБ, /tmp/bitbon-node). Для повторной проверки: git clone по URL.

## Правило разметки (D1)

Наблюдения — то, что зафиксировано в исходном коде. Факты о коде, не оценки качества.

## Наблюдения

**OBS-042.1 — форк Geth** — claim_id C-RUN5-001
- `go.mod`: module github.com/simcord-llc/bitbon-system-blockchain, go 1.15.
- Copyright в каждом файле: «Copyright Simcord LLC. This file has been modified, you can find the original version by following the link <https://github.com/ethereum/go-ethereum>».
- Структура каталогов — стандартная для go-ethereum: accounts, consensus, core, eth, p2p, trie, rlp, les, light, miner, node.
- Тип: RESULT. Статус: SUPPORTED.

**OBS-042.2 — zk-SNARK встроен в EVM (значимая модификация)** — claim_id C-RUN5-002
- `core/vm/contracts.go` содержит импорт bitbon-system-blockchain/zksnark и вызов zksnark.Verify(proof, vk, protectionCode) как precompiled contract.
- `zksnark/` (4,3 МБ) — обёртка над libsnark (C++), с заголовочными файлами, Makefile, тестами.
- Ключи: pkLen=344733, vkLen=2882, proofLen=259, hashLen=32.
- `bitbon/transfer/transfer_manager.go` использует zksnark для защиты трансферов: protectionHash, proof, GenerateKeys(constraintsLen=1000), Prove(protectionHash, pk, constraintsLen).
- Тип: RESULT. Статус: SUPPORTED.
- Значимость: интеграция zk-SNARK в EVM — нетривиальная задача. Это реальная инженерная работа.

**OBS-042.3 — 17 ABI-контрактов** — claim_id C-RUN5-003
- `bitbon/contracts/abi/`: AccessStorage, Assetbox, AssetboxInfoStorage, AssetboxStorage, Bitbon, BitbonStorage, BitbonSupport, ContractStorage, DistributionStorage, Exchange, FeeStorage, MiningAgentStorage, Otc, ReservedAliasStorage, SafeTransferStorage, Transfer.
- Go-обёртки: gen_AssetboxImpl.go, gen_BitbonImpl.go, gen_ExchangeImpl.go, gen_OtcImpl.go и др.
- Тип: RESULT. Статус: SUPPORTED.
- Значимость: контрактная инфраструктура шире, чем «один токен ERC-20». 17 контрактов — система: Assetbox, Exchange, OTC, Fee, Distribution, MiningAgent, SafeTransfer.

**OBS-042.4 — консенсус: proof-of-concept (самозаявление разработчика)** — claim_id C-RUN5-004
- `consensus/quorum/quorum.go`, строка 17: «Package quorum implements the proof-of-concept community proof-of-stake consensus engine».
- Строка 55: «QuorumEngine proof-of-concept community proof-of-stake protocol constants».
- Строка 196: «QuorumEngine is the proof-of-concept community proof-of-stake consensus engine».
- Строка 218: «New creates a QuorumEngine proof-of-concept community proof-of-stake consensus engine».
- Основан на Clique: ethDifficulty = big.NewInt(2000), uncleHash (из Clique).
- Тип: RESULT. Статус: SUPPORTED.
- Значимость: три вывода:
  1. Консенсус назван proof-of-concept самим разработчиком в комментариях кода.
  2. Это не Istanbul BFT, а переработка Clique (PoA) с элементами DPoS.
  3. Это не «разработка с нуля» — модификация существующего консенсуса.

**OBS-042.5 — размер кодовой базы** — claim_id C-RUN5-005
- 50 МБ (клон).
- Крупнейшие пакеты: signer (12 МБ), core (5,6 МБ), bitbon (4,6 МБ), zksnark (4,3 МБ), cmd (2,1 МБ).
- Тип: OBSERVATION. Статус: SUPPORTED.

**OBS-042.6 — кастомный пакет `bitbon/`** — claim_id C-RUN5-006
- `bitbon/contracts/` (3,0 МБ) — контракты.
- `bitbon/transfer/` (468 КБ) — логика трансфера с zk-SNARK.
- `bitbon/dto/` (400 КБ), `bitbon/parser/` (216 КБ), `bitbon/client/` (164 КБ).
- `bitbon/assetbox/`, `bitbon/mining_agent/`, `bitbon/noncer/`, `bitbon/fee_manager.go`, `bitbon/config.go`.
- Тип: OBSERVATION. Статус: SUPPORTED.
- Значимость: это ядро Bitbon-специфичной логики. Отдельный слой поверх Geth.

## Что это меняет в картине

**OBS-025 (Run 2)** охарактеризовал Bitbon как «форк go-ethereum, permissioned (Quorum-тип)». Верно на уровне README, но неполно. Реальный код:

1. Форк Geth — подтверждено.
2. zk-SNARK встроен в EVM — существенная кастомизация, не типовая для форков.
3. 17 ABI-контрактов — инфраструктура шире, чем «один токен».
4. Консенсус — proof-of-concept по самозаявлению разработчика.
5. Это не Istanbul BFT, а переработка Clique с элементами DPoS.

**Разрыв между заявлением и кодом:**

- Заявление: «Web 4.0», «децентрализованная информационная платформа нового поколения».
- Код: форк Geth + zk-SNARK + proof-of-concept консенсус + 17 контрактов.

Это не «пустышка». zk-SNARK интеграция — реальная инженерия. Но это и не «Web 4.0» — это форк с существенными добавлениями и PoC-консенсусом.

**Ключевой вопрос:** работает ли это на живой сети? Код есть, но permissioned. Публичной сети нет.

## UNKNOWN

- Работает ли нода на живой сети сейчас — [НЕИЗВЕСТНО].
- Оригинальна ли zk-SNARK интеграция — [НЕИЗВЕСТНО], требует сравнения.
- Качество кода (тесты, покрытие, баги) — [НЕИЗВЕСТНО], требует аудита.
- Полный список изменений относительно Geth — [НЕИЗВЕСТНО], требует diff.
- Активность разработки после 2022 — [НЕИЗВЕСТНО].

## NEXT STEP

OBS-043: сравнение с оригинальным go-ethereum — что именно изменено/добавлено. Затем — поиск технической критики в сообществах.
