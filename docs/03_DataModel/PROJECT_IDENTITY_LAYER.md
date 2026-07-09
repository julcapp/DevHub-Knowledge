# Project Identity Layer

**Код:** DATA-0002
**Версия:** 0.1.0-alpha
**Статус:** Approved Concept

## Назначение

Project Identity Layer является внутренним слоем DevHub, который связывает подтвержденную личность пользователя из Lk_uni с инженерным контекстом платформы.

## Принцип

Lk_uni отвечает на вопрос:

> Кто пользователь?

DevHub отвечает на вопросы:

> В каких проектах он участвует? Какие роли имеет? Какие действия ему разрешены?

## Модель

```
Lk_uni User
    |
    v
DevHub Identity Profile
    |
    +-- Organizations
    +-- Projects
    +-- Roles
    +-- Permissions
    +-- Activity History
    +-- Engineering Metrics
```

## Сущности

### Identity Profile

Профиль пользователя внутри DevHub.

Поля:

- user_id из Lk_uni;
- display_name;
- avatar;
- preferences;
- status;
- created_at.

### Project Membership

Связь пользователя с проектом.

Поля:

- project_id;
- user_id;
- role;
- permissions;
- joined_at;
- status.

### Engineering Activity

История инженерного вклада:

- документы;
- решения ADR;
- задачи;
- релизы;
- изменения.

## Безопасность

Lk_uni не получает бизнес-роли DevHub.

Роли и разрешения управляются внутри DevHub.

## Следующий этап

EDP-0015:

- Project Workspace;
- Role Engine;
- Permission Engine;
- Organization Membership.
