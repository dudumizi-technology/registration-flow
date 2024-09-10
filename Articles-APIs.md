
## **API Documentation: Fetch Articles**

### **Endpoint:**
`GET /api/articles/all`

### **Description:**
This API endpoint retrieves a list of articles from the database with optional filters and pagination. The articles can be filtered by `author_id`, `catid` (category ID), and whether they are trending (`is_trending`). The results are paginated and randomized.

---

### **Request Parameters:**

| Parameter      | Type      | Required | Default | Description                                                                                       |
|----------------|-----------|----------|---------|---------------------------------------------------------------------------------------------------|
| `author_id`    | integer   | No       | N/A     | Filters the articles by the given author's ID.                                                     |
| `catid`        | integer   | No       | N/A     | Filters the articles by the given category ID.                                                     |
| `is_trending`  | boolean   | No       | false   | Filters the articles by whether they are trending (based on the `hits` count). If `true`, articles with `hits > 0` are returned in descending order of hits. |
| `per_page`     | integer   | No       | 5       | Specifies the number of articles to return per page. Defaults to 5.                                |
| `page`         | integer   | No       | 1       | Specifies the page number to retrieve for paginated results.                                       |

---

### **Response:**

#### **Success Response (200 OK):**

The response will return paginated data with meta information about the pagination state.

```json
{
    "data": [
        {
            "id": 1,
            "title": "Example Article Title",
            "alias": "example-article-title",
            ...
        },
        ...
    ],
    "meta": {
        "current_page": 1,
        "last_page": 10,
        "per_page": 5,
        "total": 50
    }
}
```

- **`data`**: Contains an array of articles based on the filters and pagination.
- **`meta`**: Contains pagination information:
  - `current_page`: The current page number.
  - `last_page`: The total number of pages available.
  - `per_page`: The number of articles per page.
  - `total`: The total number of articles that match the given filters.

---

### **Example Requests:**

1. **Get all articles (default behavior)**:
    ```
    GET /api/articles/all
    ```
    - This request returns the first 5 articles, randomized and paginated.

2. **Get articles filtered by `author_id`**:
    ```
    GET /api/articles/all?author_id=5
    ```
    - Returns all articles written by author with ID 5.

3. **Get articles filtered by `catid`**:
    ```
    GET /api/articles/all?catid=3
    ```
    - Returns all articles in the category with ID 3.

4. **Get trending articles**:
    ```
    GET /api/articles/all?is_trending=true
    ```
    - Returns articles that are trending, i.e., articles with `hits > 0`, sorted by hits in descending order.

5. **Paginated articles with 10 articles per page**:
    ```
    GET /api/articles/all?per_page=10
    ```
    - Returns 10 articles per page.

6. **Get the second page of results**:
    ```
    GET /api/articles/all?per_page=10&page=2
    ```
    - Returns the second page with 10 articles per page.

---

### **Errors:**

#### **400 Bad Request:**
Occurs when invalid parameters are passed.
<!-- 
#### **404 Not Found:**
Occurs if no articles are found based on the provided filters or page number.

```json
{
    "error": "No articles found."
}
``` -->

---

### **Notes:**
- If no filters are provided, the endpoint will return all articles in random order, paginated with 5 articles per page by default.
- This endpoint supports flexible pagination and filtering, allowing clients to customize the results returned by the API.
  
---

### **Status Codes:**
- **200 OK**: Request was successful.
- **400 Bad Request**: Invalid or missing query parameters.
- **404 Not Found**: No articles found.
