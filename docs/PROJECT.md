# Project v2

Доска: **[NTO 2026 — Board](https://github.com/orgs/nto-corpsec/projects/1)** (создана, поля настроены).

Ниже — как воспроизвести с нуля: API требует скоупа `project` и GraphQL.

## Через UI

1. Организация → Projects → **New project** → Board.
2. Название: `NTO 2026 — Board`.
3. Поля:

| Поле | Тип | Значения |
|---|---|---|
| Status | single select | Backlog, Ready, In progress, Review, Done, Blocked (настроено) |
| Role | single select | lead, soceng, dfir, netsec, websec, osint |
| Priority | single select | P0, P1, P2, P3 |
| Effort | number | часы |
| Due | date | — |

4. Представления: `By role` (board, группировка Role), `P0/P1` (table, фильтр
   `priority:P0,P1`), `My work` (table, фильтр `assignee:@me`).
5. Workflows: авто-добавление issue из репозиториев организации; при закрытии issue —
   Status → Done.

## Через CLI (после `gh auth refresh -s project`)

```bash
gh project create --owner nto-corpsec --title "NTO 2026 — Board"
gh project field-create <number> --owner nto-corpsec --name Priority --data-type SINGLE_SELECT
```

Дальше — `gh project item-add` для issue или автоматизация через GraphQL.

## Правила

- Одна карточка = одна issue. Никаких «устных» задач.
- `Blocked` ставится сразу, а не в конце дня.
- Каждая карточка в `In progress` имеет assignee.
- Раз в неделю — чистка `Backlog`: что не делаем, закрываем.
