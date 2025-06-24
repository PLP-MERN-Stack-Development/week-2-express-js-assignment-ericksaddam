[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=19842308&assignment_repo_type=AssignmentRepo)
# Express.js RESTful API Assignment

This assignment focuses on building a RESTful API using Express.js, implementing proper routing, middleware, and error handling.

## Assignment Overview

You will:
1. Set up an Express.js server
2. Create RESTful API routes for a product resource
3. Implement custom middleware for logging, authentication, and validation
4. Add comprehensive error handling
5. Develop advanced features like filtering, pagination, and search

## Getting Started

1. Accept the GitHub Classroom assignment invitation
2. Clone your personal repository that was created by GitHub Classroom
3. Install dependencies:
   ```
   npm install
   ```
4. Run the server:
   ```
   npm start
   ```

## Files Included

- `Week2-Assignment.md`: Detailed assignment instructions
- `server.js`: Starter Express.js server file
- `.env.example`: Example environment variables file

## Requirements

- Node.js (v18 or higher)
- npm or yarn
- Postman, Insomnia, or curl for API testing

# Product API

## How to Run

1. Install dependencies:
   ```bash
   npm install
   ```
2. Copy `.env.example` to `.env` and set your API key:
   ```bash
   cp .env.example .env
   # Edit .env and set API_KEY
   ```
3. Start the server:
   ```bash
   node server.js
   ```

Server runs on http://localhost:3000

## API Documentation with Swagger

This project includes interactive API documentation using Swagger UI.

- After starting the server, visit: [http://localhost:3000/api-docs](http://localhost:3000/api-docs)
- You can view and test all endpoints directly from the browser.

## API Endpoints

### Authentication
All protected routes require an `x-api-key` header with the correct API key.

### Products CRUD
- `GET /api/products` — List products (supports `category`, `search`, `page`, `limit` query params)
- `GET /api/products/:id` — Get product by ID
- `POST /api/products` — Create product (protected, requires JSON body)
- `PUT /api/products/:id` — Update product (protected, requires JSON body)
- `DELETE /api/products/:id` — Delete product (protected)

#### Example Product JSON
```json
{
  "name": "Laptop",
  "description": "High-performance laptop",
  "price": 1200,
  "category": "electronics",
  "inStock": true
}
```

### Advanced Features
- `GET /api/products?category=electronics` — Filter by category
- `GET /api/products?search=laptop` — Search by name
- `GET /api/products?page=2&limit=5` — Pagination
- `GET /api/products-stats` — Product statistics (count by category)

### Error Responses
Errors return JSON with an `error` field and appropriate HTTP status code.

## Example Requests

**Create Product:**
```bash
curl -X POST http://localhost:3000/api/products \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: <your_api_key>' \
  -d '{"name":"Tablet","description":"Android tablet","price":300,"category":"electronics","inStock":true}'
```

**Get Products:**
```bash
curl http://localhost:3000/api/products
```