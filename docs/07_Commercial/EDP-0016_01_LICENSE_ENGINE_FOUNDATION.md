# EDP-0016.01 — License Engine Foundation

**Код:** COMM-0001  
**Версия:** 0.1.0-alpha  
**Статус:** Approved Concept

## Назначение

License Engine управляет коммерческой моделью DevHub: тарифами, лицензиями, возможностями и ограничениями.

## Принцип

Доступ пользователя определяется не только ролью, но и активной лицензией.

```
User
 |
 +-- License
        |
        +-- Plan
        |
        +-- Features
        |
        +-- Limits
```

## Модель тарифов

### Community

Тип:

Free

Назначение:

- знакомство с DevHub;
- индивидуальная работа;
- базовые возможности.

### Pro Personal

Тип:

Lifetime License

Цена первой версии:

4900 ₽

Возможности:

- расширенный Workspace;
- полный набор проектных функций;
- AI Hub расширенный;
- инженерная память;
- обновления согласно политике продукта.

### Update Pass

Тип:

Годовая поддержка обновлений.

Цена первой версии:

1990 ₽ / год

### Team

Тип:

Командная лицензия.

Возможности:

- организации;
- участники;
- роли;
- права;
- аудит.

## Сущности

## Plan

Хранит описание тарифа.

Поля:

- id;
- code;
- name;
- price;
- billing_type;
- features;
- limits.

## License

Хранит выданную лицензию.

Поля:

- id;
- owner_id;
- plan_id;
- status;
- created_at;
- expires_at;
- payment_reference.

Статусы:

- trial;
- active;
- expired;
- suspended;
- cancelled.

## Feature

Управляемые возможности.

Примеры:

```
AI_ADVANCED
UNLIMITED_PROJECTS
TEAM_MEMBERS
ROLE_ENGINE
AUDIT_LOG
ENTERPRISE_SECURITY
```

## License Check Flow

```
User Action
    |
    v
Permission Check
    |
    v
License Check
    |
    v
Feature Enabled?
    |
    v
Allow / Deny
```

## Пробный период

Первый запуск:

```
Trial License

Полный доступ

Ограниченный период
```

После окончания:

```
Ваш пробный период завершён

Активируйте DevHub Pro

[Купить лицензию]
```

## Интеграция платежей

Подготовить:

- ЮKassa;
- СБП;
- внутренний реестр платежей.

## Следующий этап

EDP-0016.02:

- Billing API;
- Payment Gateway;
- License Management UI;
- Feature Flags Engine.
