

# API Documentation

## 1. Check User

**Endpoint:** `/api/registration/check-user`

**Method:** `POST`

### Description:
This API endpoint checks if a user with the provided phone number already exists in the system. If the user exists, a JWT token and user profile information are returned. If the user does not exist, an error response is returned.

### Request Body:
```json
{
    "phone": "required|string|size:12"
}
```

- `phone`: A 12-character string representing the user's phone number, which should include the country code (e.g., 255, 254).

### Response:

#### Success Response:
- **Code:** `200 OK`
- **Body:**
```json
{
    "data": {
        "full_name": "John Doe",
        "phone": "255123456789",
        "image": "url_to_image",
        "access_token": "jwt_token_here"
    },
    "statusCode": 200
}
```

#### Error Responses:
- **Code:** `400 Bad Request`
- **Body:**
```json
{
    "errors": {
        "phone": ["The phone field is required."]
    }
}
```

- **Code:** `409 Conflict`
- **Body:**
```json
{
    "error": "User does not exist",
    "statusCode": 409
}
```


---

## 2. Register User

**Endpoint:** `/api/registration/register`

**Method:** `POST`

### Description:
This API endpoint registers a new user. If the registration is successful, the user's profile information and a JWT token are returned. If the user already exists, an error response is returned.

### Request Body:
```json
{
    "fullname": "required|string",
    "phone": "required|string|size:12"
}
```

- `fullname`: The full name of the user.
- `phone`: A 12-character string representing the user's phone number, which should include the country code (e.g., 255, 254).

### Response:

#### Success Response:
- **Code:** `201 Created`
- **Body:**
```json
{
    "message": "Registration successful",
    "data": {
        "full_name": "John Doe",
        "phone": "255123456789",
        "image": "url_to_image",
        "access_token": "jwt_token_here"
    },
    "statusCode": 201
}
```

#### Error Responses:
- **Code:** `400 Bad Request`
- **Body:**
```json
{
    "errors": {
        "phone": ["The phone field is required."]
    }
}
```

- **Code:** `409 Conflict`
- **Body:**
```json
{
    "error": "User already exists",
    "statusCode": 409
}
```

- **Code:** `500 Internal Server Error`
- **Body:**
```json
{
    "error": "Registration failed",
    "statusCode": 500
}
```
