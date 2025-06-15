# 🎬 Movie CRUD API in Go

This is a simple RESTful API for managing a collection of movies, built using **Go** and the **Gorilla Mux** router. It demonstrates how to perform basic CRUD operations (Create, Read, Update, Delete) with JSON data.

---

## 📦 Features

- ✅ Get all movies
- 🔍 Get a specific movie by ID
- ➕ Add a new movie
- ♻️ Update an existing movie
- ❌ Delete a movie

---

## 🚀 Getting Started

### Prerequisites

- Go 1.16+ installed. You can download it from: [https://golang.org/dl](https://golang.org/dl)

### Installation

1. **Clone the repository:**

```bash
git clone https://github.com/your-username/movie-crud-api.git
cd movie-crud-api
````

2. **Install dependencies:**

```bash
go get -u github.com/gorilla/mux
```

3. **Run the server:**

```bash
go run main.go
```

Server will start at: `http://localhost:8000`

---

## 🛠️ API Endpoints

### GET `/movies`

Fetch all movies.

**Response:**

```json
[
  {
    "id": "1",
    "isbn": "438227",
    "title": "Movie 1",
    "director": {
      "firstname": "John",
      "lastname": "Doe"
    }
  },
  ...
]
```

---

### GET `/movies/{id}`

Fetch a specific movie by ID.

**Response:**

```json
{
  "id": "1",
  "isbn": "438227",
  "title": "Movie 1",
  "director": {
    "firstname": "John",
    "lastname": "Doe"
  }
}
```

---

### POST `/movies`

Add a new movie.

**Request Body:**

```json
{
  "isbn": "123456",
  "title": "New Movie",
  "director": {
    "firstname": "Jane",
    "lastname": "Smith"
  }
}
```

---

### PUT `/movies/{id}`

Update a movie by ID.

**Request Body:**

```json
{
  "isbn": "654321",
  "title": "Updated Movie",
  "director": {
    "firstname": "Alex",
    "lastname": "Taylor"
  }
}
```

---

### DELETE `/movies/{id}`

Delete a movie by ID.

---

## ⚠️ Notes

* Data is stored **in-memory** and resets when the server restarts.
* Use tools like **Postman** or **curl** to test endpoints.
* ✅ Fix this minor issue in `main.go`:

  In your code, the delete handler is:

  ```go
  r.HandleFunc("movies/{id}", deleteMovie).Methods("DELETE")
  ```

  It should be:

  ```go
  r.HandleFunc("/movies/{id}", deleteMovie).Methods("DELETE")
  ```

---

## 🧑‍💻 Author

Built with 💙 by Sarthak Gupta

