# 🎮 GraphQL Game Reviews API

This is a simple GraphQL API for managing games, reviews, and authors using Apollo Server. It supports queries and mutations for games, authors, and reviews. Useful as a learning starter or prototype backend for small apps.

---

## 🚀 Features

- Query games, authors, and reviews
- Add, delete, and update games
- Nested relationships:
  - Games with their reviews
  - Reviews with their authors and games
  - Authors with their reviews
- Input validation using GraphQL types
- Powered by Apollo Server (standalone)

---

## 📁 Project Structure

```
.
├── _db.js             # Mock database (in-memory)
├── index.js           # Main server file
├── schema.js          # GraphQL type definitions
├── README.md          # Project documentation
```

---

## 📦 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/your-username/graphql-game-reviews.git
cd graphql-game-reviews
```

### 2. Install dependencies

```bash
npm install
```

### 3. Run the server

```bash
node index.js
```

The server will start on:

```
Server ready at: http://localhost:4000/
```

You can now access the Apollo Sandbox or any GraphQL client at this URL.

---

## 🔍 Example Queries

### Get all games

```graphql
query {
  games {
    id
    title
    platform
    reviews {
      rating
      content
    }
  }
}
```

### Add a new game

```graphql
mutation {
  addGame(game: { title: "The Witcher 3", platform: ["PC", "PS4"] }) {
    id
    title
  }
}
```

### Update a game

```graphql
mutation {
  updateGame(id: "1234", edits: { title: "The Witcher 3: Wild Hunt" }) {
    id
    title
  }
}
```

---

## 📚 Tech Stack

- Node.js
- Apollo Server (Standalone)
- GraphQL
- In-memory mock DB

---

## 🛠 Future Improvements

- Add persistent database (MongoDB, PostgreSQL, etc.)
- Add authentication/authorization
- Add pagination and filtering
- Deploy to cloud (e.g., Vercel, Render, Railway)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
