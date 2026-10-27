# hub — mission control

Единая точка входа команды: процесс, роли, runbook, решения и доска.

## Сейчас

| Что | Где |
|---|---|
| Ежедневный ритм и правила игры | [docs/PLAYBOOK.md](docs/PLAYBOOK.md) |
| Кто за что отвечает | [docs/ROLES.md](docs/ROLES.md) |
| Матрица ответственности | [docs/RACI.md](docs/RACI.md) |
| Ветки, PR, ревью | [docs/GIT-FLOW.md](docs/GIT-FLOW.md) |
| Инцидент | [runbooks/INCIDENT.md](runbooks/INCIDENT.md) |
| Утечка секрета | [runbooks/SECRET-LEAK.md](runbooks/SECRET-LEAK.md) |
| Поток флага/ответа | [runbooks/FLAG-FLOW.md](runbooks/FLAG-FLOW.md) |
| Сдача задания | [runbooks/SUBMIT.md](runbooks/SUBMIT.md) |
| Ретро | [runbooks/POSTMORTEM.md](runbooks/POSTMORTEM.md) |

## Доска

Org-level Project: [NTO 2026 — Board](https://github.com/orgs/nto-corpsec/projects/1).

Issues с метками `role/*`, `priority/*`, `status/*`; вехи `M0…M4`.
Фильтры: `is:open label:priority/p0`, `is:open label:role/websec`.

## Принципы

1. **Один поток.** Всё, что делается дольше 15 минут, становится issue.
2. **Никаких ответов в публичных репозиториях.** Флаги и решения — только в `ops`.
3. **Короткие ветки.** Ветка живёт ≤ 48 часов, иначе дробим.
4. **Передача смены — артефакт, а не рассказ.** HANDOFF-комментарий в issue.
5. **Сначала остановить кровь, потом разбираться.** Инцидент → runbook → ретро.
