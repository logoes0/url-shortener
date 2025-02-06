# URL Shortener

A simple and efficient URL shortener built using **Golang**, Docker, and Redis as the database. This project is structured to follow best practices, including separation of concerns in different folders.

## 🛠 Features

- Generate short URLs from long ones
- Redirect to the original URL using the short link
- Store and manage URLs in Redis
- Dockerized setup for easy deployment
- `.env` support for environment variables
- Tracks Rate Limit to Limit the number of requests made

## 📂 Project Structure

```
.
├── .data/                 # Persistent data storage
├── api/                   # API-related code
│   ├── database/          # Database connection and queries
│   ├── helpers/           # Utility functions
│   ├── routes/            # API route handlers
│   ├── .env               # Environment variables
│   ├── Dockerfile         # API service Dockerfile
│   ├── go.mod             # Go module dependencies
│   ├── go.sum             # Go module checksums
│   ├── main.go            # Entry point of the application
├── db/                    # Database-related setup
├── docker-compose.yml     # Docker Compose configuration file
```

## 🚀 Quick Start

### Prerequisites

Ensure you have the following installed:

- **Golang** (1.19 or later)
- **Docker & Docker Compose**
- **Make** (Optional, for convenience)

### 1️⃣ Clone the Repository

```sh
git clone https://github.com/logoes0/url-shortener.git
cd url-shortener
```

### 2️⃣ Set Up Environment Variables

Copy the `.env` file and update the necessary values:

```sh
cp api/.env.example api/.env
```

### 3️⃣ Run with Docker

```sh
docker-compose up --build
```

This will:

- Build and start the API server
- Set up the Redis database service
- Expose the necessary ports

### 4️⃣ Running Locally Without Docker

If you want to run it without Docker:

```sh
cd api
go run main.go
```

## 🏗 API Endpoints

| Method | Endpoint     | Description                  |
|--------|-------------|------------------------------|
| POST   | `/app/v1`  | Shorten a long URL           |
| GET    | `/:url`      | Redirect to the original URL |

## 🛠 Technologies Used

- **Golang** - Backend service
- **Redis** - Database storage
- **Docker & Docker Compose** - Containerization

---

