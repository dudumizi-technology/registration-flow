# Mental Health API

All endpoints in this documentation require authentication. Make sure to include the Authorization header with a valid bearer token.

---

## Mental Health Routes

### Fetch Predefined Activities

- **URL:** `/v5/mental-health/predefined-activities`
- **Method:** `GET`
- **Description:** Retrieve a list of predefined mental health activities.
- **Response:** Returns an array of predefined activities.

### Fetch Predefined Activities for a Specific Goal

- **URL:** `/v5/mental-health/predefined-activities-for-goal/{id}`
- **Method:** `GET`
- **Parameters:**
  - `id` (integer): ID of the goal to fetch associated predefined activities.
- **Description:** Retrieve predefined activities associated with a specific goal.
- **Response:** Returns an array of activities for the specified goal.

### Submit a Goal

- **URL:** `/v5/mental-health/submit-goal`
- **Method:** `POST`
- **Description:** Submit a new mental health goal.
- **Request Body:**
  ```json
  {
      "title": "Improve Sleep Quality",
      "description": "Aim to get at least 7 hours of sleep each night.",
      "targetDate": "2024-12-31"
  }
  ```
- **Response:** Returns the submitted goal details.

### Get All Submitted Goals

- **URL:** `/v5/mental-health/get-all-goals`
- **Method:** `GET`
- **Description:** Retrieve all submitted mental health goals.
- **Response:** Returns an array of all goals submitted by the user.

### Get Single Submitted Goal

- **URL:** `/v5/mental-health/get-single-submitted-goal/{id}`
- **Method:** `GET`
- **Parameters:**
  - `id` (integer): ID of the goal.
- **Description:** Fetch details of a single submitted goal.
- **Response:** Returns details of the specified goal.

### Submit an Activity

- **URL:** `/v5/mental-health/submit-activity`
- **Method:** `POST`
- **Description:** Submit a new activity related to mental health.
- **Request Body:**
  ```json
  {
      "goalId": 1,
      "activity": "Meditation",
      "duration": "30 minutes",
      "date": "2024-10-30"
  }
  ```
- **Response:** Returns the submitted activity details.

### Get All User Activities

- **URL:** `/v5/mental-health/get-all-user-activities`
- **Method:** `GET`
- **Description:** Retrieve all activities submitted by the user.
- **Response:** Returns an array of user activities.

### Get All Activities for a Specific Goal

- **URL:** `/v5/mental-health/get-all-goal-activities/{id}`
- **Method:** `GET`
- **Parameters:**
  - `id` (integer): ID of the goal to fetch activities for.
- **Description:** Retrieve activities associated with a specific goal.
- **Response:** Returns an array of activities for the specified goal.

### Get Single Activity

- **URL:** `/v5/mental-health/get-single-activities/{id}`
- **Method:** `GET`
- **Parameters:**
  - `id` (integer): ID of the activity.
- **Description:** Retrieve details of a single activity.
- **Response:** Returns details of the specified activity.

### Update Activity Completion (New)

- **URL:** `/v5/mental-health/update-activity-completion-new`
- **Method:** `POST`
- **Description:** Mark an activity as completed with updated completion logic.
- **Request Body:**
  ```json
  {
      "activityId": 1,
      "completionStatus": true,
      "dateCompleted": "2024-10-30"
  }
  ```
- **Response:** Returns the updated activity status.

### Delete Activity

- **URL:** `/v5/mental-health/delete-activity/{id}`
- **Method:** `DELETE`
- **Parameters:**
  - `id` (integer): ID of the activity to delete.
- **Description:** Delete a specific activity.
- **Response:** Returns success or error status of the deletion.

### Get All Activities

- **URL:** `/v5/mental-health/get-all-activities`
- **Method:** `GET`
- **Description:** Retrieve all mental health activities available.
- **Response:** Returns an array of all activities.

### Update Activity

- **URL:** `/v5/mental-health/update-activity`
- **Method:** `PUT`
- **Description:** Update an existing activity.
- **Request Body:**
  ```json
  {
      "id": 1,
      "activity": "Updated Meditation",
      "duration": "45 minutes",
      "date": "2024-10-30"
  }
  ```
- **Response:** Returns the updated activity details.

### Update Activity Completion

- **URL:** `/v5/mental-health/update-activity-completion`
- **Method:** `POST`
- **Description:** Mark an activity as completed.
- **Request Body:**
  ```json
  {
      "activityId": 1,
      "completionStatus": true
  }
  ```
- **Response:** Returns the updated activity status.
