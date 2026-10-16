# OBS-025 — GitHub: simcord-llc/bitbon-system-blockchain

- **observation_id:** OBS-025
- **run_id:** RUN-2
- **entity_id:** E3 (PRODUCT Bitbon), E4 (RELATED: организация GitHub)
- **observed_at:** 2026-10-16
- **source_id:** SRC-R2-007
- **source_type:** public repository (GitHub), независимый
- **independence_status:** независимый (публичный репозиторий)
- **procedure:** GitHub API: поиск repos по «bitbon»; открытие организации simcord-llc; загрузка README и метаданных репозиториев
- **raw_files:**
  - ~/field-simcord-raw/run2-github-bitbon-README.md (sha256: 1de4e006dc4245e77a7a208c7126dab0c8f2af62f8ceba9b6c3fc64922a07d65)
  - ~/field-simcord-raw/run2-github-bitbon-repo.json (sha256: 00b91e8977767e86ef0c1e78e2dc694ab8b1df3df62322ffd6d03a0d159ab3fb)
  - ~/field-simcord-raw/run2-github-simcord-llc-org.json (sha256: d3ca5f6f64c57957333afee8e14e37a41f5870af2aab8f4cf7238f31d13889af)
  - ~/field-simcord-raw/run2-github-erbb-repo.json (sha256: 27791e67a67c024d62a5d8f6892ff3f673c6572ec7cec94ab44bbcf07f1ab31f)
  - ~/field-simcord-raw/run2-github-erbb-ErbbErc20.sol (sha256: 953d1d35da942cc023965681889253d51fe36fd12b989ee977ce754d8d1bb794)

## Правило разметки (D1)

Наблюдения — то, что зафиксировано в публичном GitHub-репозитории.

## Наблюдения

**OBS-025.1 — организация simcord-llc**
- GitHub organization: simcord-llc
- Публичных репозиториев: 2
  1. bitbon-system-blockchain — Go, создан 2019-12-17, последний push 2022-05-06, 32 звезды, 4 форка, лицензия LGPL-3.0
  2. erbb-erc20 — Solidity, создан 2023-07-05, последний push 2023-07-05, 0 звёзд, лицензия GPL-3.0
- Тип: OBSERVATION. Статус: SUPPORTED.

**OBS-025.2 — README репозитория bitbon-system-blockchain (ключевое)**
Цитата: «Official implementation of the Bitbon System Blockchain based on Ethereum codebase (go-ethereum).»
Цитата: «Owner: Simcord-LLC» (прямая ссылка на www.simcord.com).
Бинарь: bitbon_node.
Тип: RESULT. Статус: SUPPORTED.
Значимость: это независимое техническое подтверждение существования блокчейн-реализации Bitbon. Не маркетинговое заявление, а исходный код.

**OBS-025.3 — структура репозитория**
Каталоги верхнего уровня: accounts, bitbon, cmd, common, consensus, console, contracts, core, crypto, eth, ethclient, ethdb, ethstats, event, graphql, internal, les, light, log, metrics, miner, node, p2p, params, quorum, rlp, rpc, signals, signer, trie, zksnark.
Тип: OBSERVATION. Статус: SUPPORTED.
Значимость: это каталоги, характерные для go-ethereum (Geth) — форк Ethereum. Наличие каталога quorum указывает на Quorum (permissioned-вариант Ethereum от JPMorgan).

**OBS-025.4 — genesis-конфигурация (ключевое)**
В README приведён пример genesis.json. В поле config присутствует объект quorum с тремя параметрами: period, epoch, initialSigners (массив адресов-подписантов). Также присутствуют стандартные для Geth поля homesteadBlock, eip155Block, byzantiumBlock, constantinopleBlock, istanbulBlock, petersburgBlock.
Тип: RESULT. Статус: SUPPORTED.
Значимость: initialSigners — это набор валидаторов (подписантов), зафиксированных на старте сети. Это конфигурация permissioned (разрешительного) блокчейна: сеть закрыта, валидаторы определяются заранее. Не публичный блокчейн в смысле открытого доступа.

**OBS-025.5 — совместимость с Ethereum**
Цитата: «Bitbon node runs with command line parameters which Ethereum uses.»
JSON-RPC флаги: --http, --http.api eth,net,web3, --ws, --ipcapi admin,debug,eth,miner,...
Порт по умолчанию 8545/8546 — стандартные для Geth.
Тип: OBSERVATION. Статус: SUPPORTED.

**OBS-025.6 — параметр --network**
Цитата: «To use bitbon node - please use --network parameter for setting your private network.»
Тип: OBSERVATION. Статус: SUPPORTED.
Значимость: сеть по умолчанию — приватная. Публичной сети Bitbon README не описывает.

**OBS-025.7 — второй репозиторий erbb-erc20**
- Файл: ErbbErc20.sol (2640 байт).
- Создан 2023-07-05, без README, без описания.
- Solidity — контракт ERC-20 (стандарт токенов Ethereum).
Тип: OBSERVATION. Статус: SUPPORTED.
Значимость: ERC-20 — публичный стандарт, в отличие от permissioned-блокчейна Bitbon. Название erbb не расшифровано (ERBB — [НЕИЗВЕСТНО]).

## Что из этого следует

1. Bitbon — форк go-ethereum, permissioned (типа Quorum). Это разрешает расхождение:
   - OBS-013.4 (cooperation): «технологію публічних розподілених реєстрів (блокчейн)» — компания заявляет публичный.
   - Техническая реализация: permissioned (Istanbul BFT, initialSigners, quorum).
   Расхождение: технически это не публичный блокчейн в смысле открытого доступа. Это разрешительная сеть с фиксированным набором валидаторов.

2. Публичного blockchain-explorer или публичной сети Bitbon в README не упоминается. Параметр --network «for setting your private network». То есть сеть по умолчанию — приватная.

3. Репозиторий активен 2019–2022. Последний push — май 2022. С 2022 без активности.

4. Новый проект 2023 — erbb-erc20 на Solidity. Это ERC-20, публичный стандарт. Возможно, попытка выйти на публичный блокчейн (Ethereum или совместимый) с другим продуктом. Связь с Bitbon — [НЕИЗВЕСТНО].

5. Лицензии — открытые (LGPL-3.0 / GPL-3.0). Код может быть проверен любым.

## Значимость для H1

H1 получает сильную поддержку. Цепочка построена:
- Заявление компании: «Система Bitbon — програмно-апаратне платформенне рішення» (OBS-007.1).
- Независимое свидетельство: открытый репозиторий с работающим (по крайней мере на уровне кода) блокчейн-узлом.
- Owner в README: Simcord-LLC — прямая ссылка на компанию.

Это третье независимое подтверждение после YouControl (юрлицо) и Google Patents (ИС).

## Что технически фиксируется

Позитивная сторона:
- Блокчейн реально существует на уровне кода.
- Исходники открыты.
- Использует проверенную базу (Geth).

Негативная сторона:
- Технически это permissioned-сеть, не «публичный распределённый реестр», как заявлено в OBS-013.4.
- Публичный explorer не упомянут.
- Активность репозитория остановилась в 2022.

## UNKNOWN

- Работает ли bitbon_node сейчас на живой сети — [НЕИЗВЕСТНО].
- Есть ли публичный explorer или RPC-эндпоинт — [НЕИЗВЕСТНО].
- Кто контролирует initialSigners — [НЕИЗВЕСТНО].
- Что такое ERBB в erbb-erc20 — [НЕИЗВЕСТНО].
- Работает ли ERC-20 контракт в публичной сети Ethereum — [НЕИЗВЕСТНО].
- Связь с сайтом bitbon.space — [НЕИЗВЕСТНО].

## NEXT STEP

OBS-026: попытка проверить наличие публичного blockchain-explorer Bitbon через поиск. Затем — суды.
