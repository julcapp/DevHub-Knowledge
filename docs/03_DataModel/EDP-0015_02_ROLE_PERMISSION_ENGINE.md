# EDP-0015.02 — Role Permission Engine

**Код:** SEC-0002  
**Версия:** 0.1.0-alpha  
**Статус:** Approved Concept

## Назначение

Role Permission Engine управляет доступом пользователей к объектам DevHub.

Основной принцип:

```
User
 ↓
Membership
 ↓
Role
 ↓
Permission
 ↓
Resource
```

---

# 1. Модель ролей

Роль является набором разрешений.

Пользователь не получает права напрямую.

Пример:

```
Александр
 ↓
Owner проекта DevHub
 ↓
Project Owner Role
 ↓
Create / Edit / Manage
```

---

# 2. Базовые роли

| Роль | Назначение |
|---|---|
| System Administrator | Полное управление платформой |
| Organization Administrator | Управление организацией |
| Project Owner | Владелец проекта |
| Project Manager | Управление проектом |
| Architect | Архитектура и решения |
| Developer | Код и технические изменения |
| Analyst | Требования и документы |
| Quality Engineer | Качество, аудит, проверки |
| Observer | Только просмотр |

---

# 3. Уровни прав

## Platform Level

Вся система DevHub.

Примеры:

- управление организациями;
- настройки безопасности;
- управление пользователями.

## Organization Level

Организация.

Примеры:

- приглашение сотрудников;
- политики доступа.

## Project Level

Конкретный проект.

Примеры:

- документы;
- код;
- участники;
- AI настройки.

## Resource Level

Отдельный объект.

Примеры:

- документ;
- ADR;
- файл;
- задача.

---

# 4. Примеры разрешений

```
project.read
project.update
project.delete
member.invite
member.manage
role.assign
document.read
document.edit
adr.create
release.publish
ai.configure
```

---

# 5. Наследование

Пример:

```
Organization Admin
        |
        +-- Project Manager
                 |
                 +-- Developer
```

Но права могут быть ограничены политикой проекта.

---

# 6. Проверка доступа

Каждый запрос проходит проверку:

```
User
 ↓
Active Session
 ↓
Project Membership
 ↓
Role
 ↓
Permission Check
 ↓
Action
```

---

# 7. Аудит

Каждое изменение прав фиксируется:

- кто изменил;
- кому изменили;
- старая роль;
- новая роль;
- время;
- проект.

---

# Следующий этап

EDP-0015.03:

- Organization Membership;
- Tenant Model;
- подготовка Enterprise режима.
