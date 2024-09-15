# Auth API Spec

## Register

Endpoint: POST /api/auth/register

Request Body

```json
{
    "username": "clara",
    "password": "clara010203",
    "name": "Clara Fallin"
}
```

Response Body (success)

```json
{
    "status": "OK",
    "code": 200,
    "data": {
        "username": "Clara",
        "password": "clara010203",
        "name": "Clara Fallin"
    }
}

```
Response Body (failed)

```json
{
    "status": "FAILED",
    "code": 400,
    "error": "Username already exist"
}
```

## Login

Endpoint: POST /api/auth

Request Body

```json
{
    "username": "clara",
    "password": "clara010203",
}
```

Response Body (success)

```json
{
    "status": "OK",
    "code": 200,
    "data": {
        "token": "generated_uuid",
        "expiredAt": 1234567
    }
}

```
Response Body (failed)

```json
{
    "status": "FAILED",
    "code": 400,
    "error": "Username or Password is wrong"
}
```

## Get Current User

Endpoint: GET /api/auth

Header:
 - Authorization: token

Response Body (success)

```json
{
    "status": "OK",
    "code": 200,
    "data": {
        "username": "Clara",
        "name": "Clara Fallin"
    }
}

```
Response Body (failed)

```json
{
    "status": "FAILED",
    "code": 400,
    "error": "Unauthorized"
}
```

## Logout User

Endpoint: DELETE /api/auth

Header:
 - Authorization: token

Response Body (success)

```json
{
    "status": "OK",
    "code": 200
}
```
