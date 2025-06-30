# User API Spec

## Register User API

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "maulana",
  "password": "secret",
  "name": "Asyifa Maulana"
}
```

Response Body Success :

```json
{
  "data": {
    "username": "maulana",
    "name": "Asyifa Maulana"
  }
}
```

Response Body Error :

```json
{
  "errors": "Username already registered"
}
```

## Login User API

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "maulana",
  "password": "secret"
}
```

Response Body Success :

```json
{
  "data": {
    "token": "unique-token"
  }
}
```

Response Body Error :

```json
{
  "errors": "Username or Password wrong"
}
```

## Update User API

Endpoint : PATCH /api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "name": "new name", // optional
  "password": "new password" //optional
}
```

Response Body Success :

```json
{
  "data": {
    "username": "maulana",
    "name": "new name"
  }
}
```

Response Body Error :

```json
{
  "errors": "Name Length max 100"
}
```

## Get User API

Endpoint : GET /api/users/current

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": {
    "username": "maulana",
    "name": "Asyifa Maulana"
  }
}
```

Response Body Error :

```json
{
  "errors": "Unauthorized"
}
```

## Logout User API

Endpoint : DELETE /api/users/logout

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :

```json
{
  "errors": "Unathorized"
}
```
