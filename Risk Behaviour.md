# API Documentation

## 1. Submit Risk Factor

**Endpoint:** `/api/risk-behavior/submit-result`

**Method:** `POST`

### Description:

This API endpoint submits a user's risk behavior assessment by storing the responses to 15 questions and the total score in the database.

### Request Body:

```json
{
    "answerValues": [
        "string_or_integer" // Array of 15 elements representing the user's answers to the risk behavior questions
    ],
    "totalScore": "required|numeric" // Total score calculated based on the user's responses
}
```

-   `answerValues`: An array of 15 elements, each representing the user's response to a specific risk behavior question. The responses can be either strings or integers.
-   `totalScore`: A numeric value representing the total score calculated based on the user's responses.

### Response:

#### Success Response:

-   **Code:** `200 OK`
-   **Body:**

```json
{
    "value": true,
    "message": "Successfully added"
}
```

#### Error Responses:

-   **Code:** `400 Bad Request`
-   **Body:**

```json
{
    "errors": {
        "answerValues": [
            "The answerValues field is required and must contain exactly 15 elements."
        ],
        "totalScore": ["The totalScore field is required and must be numeric."]
    }
}
```

### Database Structure:

The `answerValues` should be in the following format:

i.e `answerValues` = `[qn1, qn2, ... qn15]`

| Field  | Type     | Description                                             |
| ------ | -------- | ------------------------------------------------------- |
| `qn1`  | longtext | Age of the respondent                                   |
| `qn2`  | longtext | Gender of the respondent                                |
| `qn3`  | longtext | Region where the respondent lives                       |
| `qn4`  | int(11)  | Response to the question about occupation               |
| `qn5`  | int(11)  | Response to the question about circumcision             |
| `qn6`  | int(11)  | Response to the question about multiple sexual partners |
| `qn7`  | int(11)  | Response to the question about unprotected sex          |
| `qn8`  | int(11)  | Response to the question about HIV-positive partner     |
| `qn9`  | int(11)  | Response to the question about anal sex                 |
| `qn10` | int(11)  | Response to the question about sex under alcohol        |
| `qn11` | int(11)  | Response to the question about injecting drugs          |
| `qn12` | int(11)  | Response to the question about sharing sharp objects    |
| `qn13` | int(11)  | Response to the question about sex work                 |
| `qn14` | int(11)  | Response to the question about STIs                     |
| `qn15` | int(11)  | Response to the question about mental health challenges |
