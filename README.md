# User Management API

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Brianamol/user-api.git
   cd user-api
   ```
2. Install dependencies:
   ```bash
   npm install express
   ```
3. Start the server:
   ```bash
   node index.js
   ```
4. API will be available at `http://localhost:3000`.

## API Endpoints

### Get All Users

- **URL**: `/api/users`
- **Method**: `GET`
- **Success Response**:
  - Code: 200
  - Content: `[ { id: 1, name: "John", email: "john@example.com" }, ... ]`

### Get User by ID

- **URL**: `/api/users/:id`
- **Method**: `GET`
- **URL Params**: `id=[integer]`
- **Success Response**:
  - Code: 200
  - Content: `{ id: 1, name: "John", email: "john@example.com" }`
- **Error Response**:
  - Code: 404
  - Content: `{ message: "User not found" }`

### Create a New User

- **URL**: `/api/users`
- **Method**: `POST`
- **Body**:
  ```json
  {
    "name": "New User",
    "email": "newuser@example.com"
  }
  ```
- **Success Response**:
  - Code: 201
  - Content: `{ id: 3, name: "New User", email: "newuser@example.com" }`
- **Error Response**:
  - Code: 400
  - Content: `{ message: "Name and email are required" }`

### Update a User

- **URL**: `/api/users/:id`
- **Method**: `PUT`
- **Body**:
  ```json
  {
    "name": "Updated User",
    "email": "updateduser@example.com"
  }
  ```
- **Success Response**:
  - Code: 200
  - Content: `{ id: 1, name: "Updated User", email: "updateduser@example.com" }`
- **Error Response**:
  - Code: 404
  - Content: `{ message: "User not found" }`
  - Code: 400
  - Content: `{ message: "Name and email are required" }`

### Delete a User

- **URL**: `/api/users/:id`
- **Method**: `DELETE`
- **Success Response**:
  - Code: 204
- **Error Response**:
  - Code: 404
  - Content: `{ message: "User not found" }`

## Error Handling

All errors return JSON responses with a `message` field explaining the issue.

## License

MIT License
