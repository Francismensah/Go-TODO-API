```markdown
# Go TODO API

A simple REST API for managing todos built with Go and the Gin web framework.

## Features

- List all todos
- Get a specific todo by ID
- Create new todos
- Toggle todo completion status
- JSON response format
- Built-in request logging and error handling

## Prerequisites

- Go 1.16 or higher
- [Gin Web Framework](https://github.com/gin-gonic/gin)

## Installation

1. Clone the repository
```bash
git clone https://github.com/Francismensah/Go-TODO-API.git
cd todo-api
```

2. Install dependencies
```bash
go mod init todo-api
go get github.com/gin-gonic/gin
```

3. Run the server
```bash
go run main.go
```

The server will start on `localhost:8080`

## API Endpoints

### GET /todos
Returns a list of all todos.

Response:
```json
[
  {
    "id": "1",
    "item": "Buy milk",
    "completed": false
  },
  {
    "id": "2",
    "item": "Clean room",
    "completed": false
  }
]
```

### GET /todos/:id
Returns a specific todo by ID.

Response:
```json
{
  "id": "1",
  "item": "Buy milk",
  "completed": false
}
```

### POST /todos
Creates a new todo.

Request body:
```json
{
  "id": "4",
  "item": "Learn Go",
  "completed": false
}
```

### PATCH /todos/:id
Toggles the completion status of a todo.

Response:
```json
{
  "id": "1",
  "item": "Buy milk",
  "completed": true
}
```

## Error Handling

The API returns appropriate HTTP status codes:
- 200: Successful operation
- 201: Successfully created a new todo
- 404: Todo not found
- 400: Invalid request body

## Data Structure

```go
type todo struct {
    ID        string `json:"id"`
    Item      string `json:"item"`
    Completed bool   `json:"completed"`
}
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is NOT licensed
```