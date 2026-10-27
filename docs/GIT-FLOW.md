# Git-flow команды

## Модель

Trunk-based development. `main` всегда работоспособен и защищён.

```
main ──●────────●─────────●────────●──▶
        \      /          \      /
         ●──●─●            ●──●─●
        feat/websec/sqli   fix/dfir/evtx-chunk
```

- Ветка от `main`, живёт ≤ 48 часов, мерж — squash.
- Прямой push в `main` запрещён ruleset'ом, включая администраторов.
- Force-push в `main` запрещён; в своей ветке — можно.

## Именование

`<тип>/<роль>/<краткий-слаг>`: `feat/websec/sqli-gen`, `fix/netsec/pcap-ts`,
`docs/hub/handoff`, `intel/lead/domain-map`, `writeup/dfir/task-07`.

## Коммиты

Conventional Commits. Заголовок ≤ 72 символов, английский, императив.
Тело — почему, а не что. `Refs #12`, `Closes #12`.

## PR

1. Draft → готово → `status/needs-review` + CODEOWNER.
2. CI обязателен: джоба `gate` должна быть зелёной (внутри — lint, test, security, no-leak).
3. Один approve от CODEOWNER, для `main` — от лида.
4. Squash-merge, ветка удаляется автоматически.
5. Не мержим «на красном» и не отключаем проверки ради скорости.

## Hotfix

Только при блокере этапа: ветка `fix/<role>/hotfix-<slug>`, один ревьюер,
мерж немедленно, ретро в течение 24 часов. Если правили ruleset — фиксируем в ADR.

## Теги

`v0.1.0` — после M1, `v0.2.0` — после M2, `v1.0.0` — после этапа.
Тег ставит лид, аннотированный, с описанием состава.
