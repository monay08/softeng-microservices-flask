# 📝 Microservices API Documentation

This documentation covers the **User Service** and **Order Service** APIs.

---

## 🛠️ Base URLs

- **User Service**: `http://localhost:5000`
- **Order Service**: `http://localhost:5001`

---

## 📌 User Service (Registration)
Handles user registration and retrieval.

### 🔹 **Register a User**
- **Endpoint**: `POST /register`
- **Description**: Registers a new user.
- **Request Body (JSON)**:
  ```json
  {
    "name": "Levi Miller",
    "email": "levimiller@yahoo.com",
    "password": "iloveyou"
  }
  ```
- **Response (Success)**: `201 Created`
  ```json
  {
    "message": "User registered successfully!"
  }
  ```
- **Response (Error: Email already exists)**: `400 Bad Request`
  ```json
  {
    "error": "Email already exists."
  }
  ```
- **Response (Error: Missing fields)**: `400 Bad Request`
  ```json
  {
    "error": "Missing required fields"
  }
  ```

---

### 🔹 **Get All Users**
- **Endpoint**: `GET /users`
- **Description**: Retrieves a list of registered users.
- **Response (Success: 200 OK)**
  ```json
  [
    { "id": 1, "name": "Levi Miller", "email": "levimiller@yahoo.com" },
    { "id": 2, "name": "Jane Doe", "email": "jane@example.com" }
  ]
  ```

---

## 📌 Order Service
Handles order creation and retrieval.

### 🔹 **Create an Order**
- **Endpoint**: `POST /orders`
- **Description**: Creates a new order.
- **Request Body (JSON)**:
  ```json
  {
    "user_id": 1,
    "product": "huawei y6s",
    "quantity": 2
  }
  ```
- **Response (Success: 201 Created)**:
  ```json
  {
    "message": "Order created successfully!",
    "order_id": 123
  }
  ```
- **Response (Error: User Not Found)**: `400 Bad Request`
  ```json
  {
    "error": "User does not exist."
  }
  ```

---

### 🔹 **Get All Orders**
- **Endpoint**: `GET /orders`
- **Description**: Retrieves a list of all orders.
- **Response (Success: 200 OK)**
  ```json
  [
    { "order_id": 123, "user_id": 1, "product": "Laptop", "quantity": 2 },
    { "order_id": 124, "user_id": 2, "product": "Phone", "quantity": 1 }
  ]
  ```

---

## ⚙️ Environment Variables
| Variable       | Description                         | Example Value           |
|---------------|-------------------------------------|-------------------------|
| `DB_HOST`     | Database hostname                  | `db`                    |
| `DB_USER`     | Database username                  | `root`                  |
| `DB_PASSWORD` | Database password                  | `root`                  |
| `DB_NAME`     | Database name                      | `microservices_db`      |
| `USER_SERVICE_URL` | URL of User Service (for Order Service) | `http://localhost:5000` |

---

## 🏃 Running the Services with Docker
```sh
docker-compose up --build
```

This will start:
- **MySQL** on port `3307`
- **User Service** on port `5000`
- **Order Service** on port `5001`

---