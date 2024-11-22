# TaskMasterAPI

TaskMasterAPI is a RESTful API built to manage tasks effectively. It allows users to perform CRUD operations on tasks, track their completion status, and sort/filter them based on various attributes. This project provides a backend solution for managing personal or work-related tasks, with simple yet efficient endpoints.

## Features

- **Create tasks**: Add a new task with a title, description, priority, and completion status.
- **Retrieve tasks**: Fetch all tasks or filter by completion status or priority level.
- **Update tasks**: Modify existing tasks by updating their details.
- **Delete tasks**: Remove tasks by ID.
- **Filter tasks**: Get tasks by their completion status and priority.

## Technologies Used

- **Node.js**: Backend server.
- **Express.js**: Web framework for building the API.
- **Ajv**: JSON schema validation library to ensure data integrity.
- **FS (File System)**: Handling JSON file storage for tasks data.

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/rajanarahul93/TaskMasterAPI.git
   cd TaskMasterAPI
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Start the server**:
   ```bash
   npm start
   ```
   The server will be running on `http://localhost:3000`.

## API Endpoints

### 1. **GET /tasks**
Retrieve all tasks. You can filter tasks by completion status or sort them by creation date.

**Query Parameters**:
- `completed`: Optional. Filter tasks based on their completion status (`true` or `false`).
- `sort`: Optional. Sort tasks by their creation date (`desc` or `asc`).

**Example**:
```bash
curl -X GET "http://localhost:3000/tasks?completed=true&sort=desc"
```

### 2. **GET /tasks/:id**
Retrieve a task by its ID.

**Example**:
```bash
curl -X GET "http://localhost:3000/tasks/1"
```

### 3. **GET /tasks/priority/:level**
Retrieve tasks filtered by their priority (`low`, `medium`, or `high`).

**Example**:
```bash
curl -X GET "http://localhost:3000/tasks/priority/medium"
```

### 4. **POST /tasks**
Create a new task with the required data (title, description, completed, and priority).

**Example**:
```bash
curl -X POST "http://localhost:3000/tasks" --header "Content-Type: application/json" --data '{"id":"7","title":"Task 7","description":"This is task 7","completed":false,"priority":"medium"}'
```

### 5. **PUT /tasks/:id**
Update an existing task by its ID.

**Example**:
```bash
curl -X PUT "http://localhost:3000/tasks/7" --header "Content-Type: application/json" --data '{"title":"Updated Task 7","description":"Updated description","completed":true,"priority":"high"}'
```

### 6. **DELETE /tasks/:id**
Delete a task by its ID.

**Example**:
```bash
curl -X DELETE "http://localhost:3000/tasks/7"
```

## Error Handling

The API responds with appropriate HTTP status codes:
- **400**: Bad Request (Invalid task data)
- **404**: Not Found (Task not found)
- **500**: Internal Server Error (Unexpected issues)

Example error response:
```json
{
  "message": "Invalid task data"
}
```

## File Storage

Tasks are stored in a JSON file (`tasks.json`) located in the root directory. The file is read and updated on each API call to persist task data.

## Contributing

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Commit your changes.
4. Push to your forked repository.
5. Submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to open an issue or submit a pull request if you find any bugs or want to suggest improvements!

```

### Key Points:
- **Project name**: `TaskMasterAPI`
- **Installation**: Instructions to clone, install dependencies, and run the server.
- **API Endpoints**: Description of the API endpoints with usage examples.
- **Error handling**: Proper error responses for different situations (client-side and server-side errors).
- **Contributing**: Instructions for contributing to the project.