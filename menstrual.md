
### Endpoints

---

#### 1. **Get Menstrual Partners**
   - **URL**: `/api/menstrual/get-partners`
   - **Method**: `GET`
   - **Authentication**: `Bearer Token`
   - **Description**: Fetches the list of menstrual partners.
   - **Response**:
     - `200 OK`: A list of menstrual partners.
     - `401 Unauthorized`: User is not authenticated.

---

#### 2. **Update Menstrual Partner**
   - **URL**: `/api/menstrual/update-menstrual`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Updates information about a menstrual partner.
   - **Body Parameters**:
     - `phone` (numeric): Phone number of the partner.
   - **Response**:
     - `200 OK`: Successfully Message.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 3. **Remove Menstrual Partner**
   - **URL**: `/api/menstrual/remove-menstrual`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Removes a menstrual partner.
   - **Body Parameters**:
     - `id` (numeric): ID of the partner to remove.
   - **Response**:
     - `200 OK`: Partner removed successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 4. **Notify Menstrual Partner**
   - **URL**: `/api/menstrual/notify-partners`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Sends notifications to menstrual partners.
   - **Response**:
     - `200 OK`: Notification sent successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 5. **Get Menstrual Questions**
   - **URL**: `/api/menstrual/menstrual-questions`
   - **Method**: `GET`
   - **Authentication**: `Bearer Token`
   - **Description**: Fetches all available menstrual-related questions.
   - **Response**:
     - `200 OK`: List of questions.
     - `401 Unauthorized`: User is not authenticated.

---

#### 6. **Get Message**
   - **URL**: `/api/menstrual/get-message`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Retrieves a specific message related to menstrual calculation values.
   - **Body Parameters**:
     - `results` (numeric): ID of the message to retrieve.
   - **Response**:
     - `200 OK`: The message content.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 7. **Submit Menstrual Question**
   - **URL**: `/api/menstrual/question-submission`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Submits answers for menstrual questions.
   - **Body Parameters**:
     - `menstrual_questions_id` (numeric)
     - `menstrual_challenge_result_id` (numeric)
     - `answer` (String)
   - **Response**:
     - `200 OK`: Question submitted successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 8. **Submit Menstrual Result**
   - **URL**: `/api/menstrual/result-submission`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Submits menstrual-related results.
   - **Body Parameters**:
     - `value` (numeric)
     - `action` (string)
   - **Response**:
     - `200 OK`: Result submitted successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 9. **Submit Result Action**
   - **URL**: `/api/menstrual/result-submission-action`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Submits an action based on menstrual results.
   - **Body Parameters**:
     - `id` (numeric)
     - `value` (string)
   - **Response**:
     - `200 OK`: Action submitted successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 10. **Update Last Menstrual Period**
   - **URL**: `/api/menstrual/updateLastMenstrualPeriod`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Updates the last recorded menstrual period date.
   - **Body Parameters**:
     - `date` (string): The last menstrual period date.
   - **Response**:
     - `200 OK`: Last menstrual period updated successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 11. **Update Menstrual Settings**
   - **URL**: `/api/menstrual/updateMenstrualSettings`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Updates menstrual-related settings.
   - **Body Parameters**:
     - `menstrual_date` (string)
     - `days_last` (numeric)
     - `days_duration` (numeric)
   - **Response**:
     - `200 OK`: Settings updated successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 12. **Update Notification Settings**
   - **URL**: `/api/menstrual/updateNotificationSettings`
   - **Method**: `POST`
   - **Authentication**: `Bearer Token`
   - **Description**: Updates notification preferences related to menstrual data.
   - **Body Parameters**:
     - `period_alert` (required|numeric|in:0,1)
     - `ovulation_alert` (required|numeric|in:0,1)
   - **Response**:
     - `200 OK`: Notification settings updated successfully.
     - `400 Bad Request`: Invalid input data.
     - `401 Unauthorized`: User is not authenticated.

---

#### 13. **Get Menstrual Settings**
   - **URL**: `/api/menstrual/getMenstrualSetting`
   - **Method**: `GET`
   - **Authentication**: `Bearer Token`
   - **Description**: Fetches the current menstrual-related settings.
   - **Response**:
     - `200 OK`: The current settings.
     - `401 Unauthorized`: User is not authenticated.

---

