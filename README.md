# E-Commerce Platform

A MERN-based e-commerce application with a React client and an Express.js REST API backed by MongoDB. The backend is organized into routes, controllers, models, middleware, and helper modules.

## Tech Stack

- **Frontend:** React, Ant Design, React Icons
- **Backend:** Node.js, Express.js
- **Database:** MongoDB with Mongoose
- **Authentication & Security:** JSON Web Tokens (JWT), bcrypt password hashing, role-based admin middleware
- **Payments:** Braintree
- **Other tools:** dotenv, Morgan, CORS, express-formidable

## Features

### Authentication & user accounts
- User registration and login
- Password hashing with bcrypt
- JWT-based authentication
- Protected user and administrator routes
- Profile updates and password recovery

### Product catalogue
- Create, update, and retrieve products
- Product categories and category-based browsing
- Product image handling
- Product search and price/category filters
- Related products
- Product count and paginated product listing

### Orders & payments
- Retrieve a user's orders
- Administrator order listing and order-status updates
- Braintree client-token generation and payment processing

### Administration
- Role-protected product and category management
- Separate user and administrator authorization middleware

## Project Structure

```text
.
├── client/          # React client build
├── config/          # MongoDB connection
├── controllers/     # Request handlers and business logic
├── helpers/         # Authentication helpers
├── middlewares/     # JWT and administrator authorization
├── models/          # Mongoose data models
├── routes/          # Express API routes
├── server.js        # Express application entry point
├── package.json
└── README.md
```

## Getting Started

### Prerequisites

- Node.js and npm
- MongoDB connection string
- Braintree sandbox credentials for payment functionality

### 1. Clone the repository

```bash
git clone https://github.com/MOHAMMED-RIYAZ/Ecommerce.git
cd Ecommerce
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
PORT=8080
DEV_MODE=development
MONGO_URL=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
BRAINTREE_MERCHANT_ID=your_braintree_merchant_id
BRAINTREE_PUBLIC_KEY=your_braintree_public_key
BRAINTREE_PRIVATE_KEY=your_braintree_private_key
```

Keep credentials private. Do not commit your `.env` file.

### 4. Start the server

```bash
npm start
```

The API server uses port `8080` by default. Set `PORT` in your environment to use another port.

## API Overview

The API is grouped under the following base paths:

| Base path | Purpose |
|---|---|
| `/api/v1/auth` | Registration, login, profile, authentication and orders |
| `/api/v1/category` | Product category operations |
| `/api/v1/product` | Product catalogue, search, filters and payments |

Examples of implemented endpoints:

- `POST /api/v1/auth/register`
- `POST /api/v1/auth/login`
- `GET /api/v1/auth/user-auth`
- `GET /api/v1/auth/orders`
- `GET /api/v1/category/get-category`
- `GET /api/v1/product/get-product`
- `GET /api/v1/product/search/:keyword`
- `GET /api/v1/product/product-list/:page`
- `GET /api/v1/product/braintree/token`
- `POST /api/v1/product/braintree/payment`

Protected endpoints require the JWT authorization header. Administrator operations additionally require an administrator role.

## What This Project Demonstrates

- Building REST APIs with Express.js
- Structuring a Node.js application using MVC-style separation
- Modeling application data with MongoDB and Mongoose
- Implementing JWT authentication and role-based authorization
- Handling product images, filtering, search, and pagination
- Integrating a payment gateway

## Author

**Mohammed Riyaz**

- GitHub: [MOHAMMED-RIYAZ](https://github.com/MOHAMMED-RIYAZ)
- LinkedIn: [Connect on LinkedIn](https://www.linkedin.com/in/mohammedriyazba564721b/)
- Portfolio: [Visit portfolio](https://riyaz-portfolio-eight.vercel.app)
