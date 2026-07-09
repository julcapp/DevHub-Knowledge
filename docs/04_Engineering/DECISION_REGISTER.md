# Decision Register

**Документ:** DECISION_REGISTER.md  
**Код:** ENG-0001  
**Версия:** 1.0.0-alpha  
**Статус:** Active  
**Ответственный:** CTO

## Назначение

Реестр фиксирует утверждённые решения проекта DevHub, чтобы они не оставались только в переписке.

## Статусы

- Approved — принято;
- In Progress — в работе;
- Implemented — реализовано;
- Deferred — отложено;
- Rejected — отклонено.

## Реестр решений

| ID | Решение | Статус | Связанные документы | Реализация |
|---|---|---|---|---|
| DEC-0001 | GitHub является официальным источником инженерных решений | Approved | PRODUCT_PRINCIPLES.md | FP-001 |
| DEC-0002 | Пользовательский интерфейс DevHub должен быть русскоязычным | Approved | GLOSSARY.md, PRODUCT_PRINCIPLES.md | EDP-0011 |
| DEC-0003 | Проект является главной сущностью DevHub | Approved | DEVHUB_CONSTITUTION.md, PRODUCT_VISION.md | EDP-0010 |
| DEC-0004 | AI Hub подключает модели через провайдеров | Approved | PRODUCT_BACKLOG.md, DEVHUB_2030.md | EDP-0012 |
| DEC-0005 | Инженерная память является ключевой ценностью DevHub | Approved | WHY.md, DEVHUB_2030.md | FP-002 / Beta |
| DEC-0006 | Lk_uni принимается как базовая Identity & Auth Platform для DevHub | Approved | LK_UNI_INTEGRATION.md, USER_IDENTITY_MODEL.md | EDP-0013–EDP-0017 |
| DEC-0007 | Пользователь DevHub может иметь несколько identities | Approved | USER_IDENTITY_MODEL.md | EDP-0013 |
| DEC-0008 | Роли и права DevHub строятся через ProjectMember → Role → Permissions | Approved | USER_IDENTITY_MODEL.md | EDP-0015 |
| DEC-0009 | Все входы, восстановления доступа и изменения прав должны журналироваться | Approved | USER_IDENTITY_MODEL.md, LK_UNI_INTEGRATION.md | EDP-0016 |

## Следующее обновление

Реестр будет расширен в FP-002 и связан с ADR, Requirements Register и Engineering Diary.
