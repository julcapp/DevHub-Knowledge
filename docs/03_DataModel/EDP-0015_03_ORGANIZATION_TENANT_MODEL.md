# EDP-0015.03 — Organization & Tenant Model

**Код:** DATA-0003  
**Версия:** 0.1.0-alpha  
**Статус:** Approved Concept

## Назначение

Модель организаций подготавливает DevHub к корпоративному использованию.

Она позволяет одной платформе обслуживать несколько независимых команд и компаний.

---

# 1. Архитектурный принцип

DevHub строится как multi-tenant платформа.

```
DevHub Platform
      |
      +-- Organization A
      |       |
      |       +-- Users
      |       +-- Projects
      |       +-- Policies
      |
      +-- Organization B
              |
              +-- Users
              +-- Projects
              +-- Policies
```

---

# 2. Organization

Организация — верхний уровень владения ресурсами.

Поля:

- id;
- name;
- description;
- owner_id;
- status;
- created_at;
- security_policy.

---

# 3. Organization Member

Пользователь может состоять в нескольких организациях.

```
User
 |
 +-- Organization Membership
          |
          +-- Organization Role
```

Поля:

- user_id;
- organization_id;
- role;
- status;
- joined_at.

---

# 4. Проекты организации

```
Organization
      |
      +-- Projects
              |
              +-- Members
              +-- Documents
              +-- Code
              +-- AI Settings
```

---

# 5. Изоляция данных

Каждый запрос должен учитывать:

```
Organization Context
        +
User Identity
        +
Permissions
```

Пользователь не должен видеть ресурсы другой организации.

---

# 6. Корпоративные политики

Организация может задавать:

- требования к сессиям;
- обязательные способы входа;
- разрешённые AI-провайдеры;
- правила хранения документов;
- политики безопасности.

---

# 7. Связь с Lk_uni

Lk_uni предоставляет:

- личность пользователя;
- способы идентификации;
- подтверждение входа.

DevHub Organization Layer предоставляет:

- принадлежность к компании;
- роли;
- политики;
- доступ к проектам.

---

# Следующий этап

EDP-0015.04:

- окончательная модель пользователей и ролей;
- подготовка API моделей;
- переход к реализации Auth Gateway.
