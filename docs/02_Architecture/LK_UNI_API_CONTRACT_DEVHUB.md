# Lk_uni ↔ DevHub API Contract

**Статус:** Draft for EDP-0013.01  
**Версия:** 0.1.0-alpha

## Назначение

Документ определяет минимальный контракт взаимодействия DevHub и Lk_uni.

## 1. Авторизация

### Login

DevHub перенаправляет пользователя в Lk_uni.

После успешной проверки Lk_uni возвращает:

```json
{
  "user_id": "USR-001",
  "access_token": "token",
  "expires_at": "date"
}
```

## 2. Получение пользователя

Endpoint:

```text
GET /api/auth/me
```

Ответ:

```json
{
  "id": "USR-001",
  "name": "User Name",
  "status": "verified",
  "identities": [
    {
      "provider": "email",
      "verified": true
    }
  ]
}
```

## 3. События безопасности

DevHub должен получать или фиксировать:

- успешный вход;
- неуспешный вход;
- выход;
- восстановление доступа;
- изменение идентификатора;
- изменение роли.

## 4. Роли

Lk_uni подтверждает пользователя.

DevHub определяет права внутри проекта:

```text
User
 ↓
ProjectMember
 ↓
Role
 ↓
Permissions
```

## 5. Ограничения

Lk_uni не хранит бизнес-логику DevHub.

DevHub не хранит секреты авторизации Lk_uni.

## 6. Следующая версия

Версия 1.0 будет подготовлена после проверки реального API Lk_uni.
