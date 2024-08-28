
# API Documentation

## Overview

This API allows you to interact with our services. To access protected endpoints, you need to authenticate your requests using an API key.

### Authentication

To authenticate your requests, you must include an API key in the request headers. The API key is used to identify the client making the request and determine access permissions.

### How to Pass API Key in the Header

You need to include your API key in the `X-API-KEY` header for each request. Below is an example of how to do this.

### Example Request with API Key

#### cURL

```bash
curl -X GET "https://api.example.com/protected-endpoint" \
-H "X-API-KEY: your-api-key-here" \
-H "Content-Type: application/json"
```

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
