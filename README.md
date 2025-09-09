# 🌱 Agriculture E-Commerce Web Application

## 📌 Project Overview

This is a **full-stack web application** for buying and selling
**agriculture products** such as seeds, fertilizers, vegetables, fruits,
and tools.\
It allows **farmers** to list their products, **buyers** to purchase
them, and **admins** to manage users, products, and orders.

------------------------------------------------------------------------

## 🚀 Features

-   👨‍🌾 **Farmer Dashboard** -- Upload & manage agriculture products.\
-   🛒 **E-commerce Features** -- Product browsing, cart, checkout.\
-   💳 **Payment Gateway** -- Secure online payments (Razorpay/Stripe).\
-   🔑 **Authentication** -- JWT-based login/signup.\
-   📦 **Order Management** -- Track orders (pending, shipped,
    delivered).\
-   📊 **Admin Panel** -- Approve products, manage users, sales reports.

------------------------------------------------------------------------

## 🛠 Tech Stack

### Frontend

-   React.js\
-   Material UI (MUI)\
-   Redux Toolkit (state management)\
-   React Router (navigation)\
-   Axios (API calls)

### Backend

-   Node.js + Express.js\
-   MongoDB + Mongoose\
-   JWT Authentication\
-   Razorpay / Stripe (payments)

### Deployment

-   Frontend → Vercel / Netlify\
-   Backend → Render / Railway\
-   Database → MongoDB Atlas

------------------------------------------------------------------------

## 🏗 System Architecture

    Frontend (React + MUI + Redux) 
            │
            ▼
    Backend (Node.js + Express API) 
            │
     ┌──────┼─────────┬─────────┐
     ▼      ▼         ▼
    MongoDB JWT   Payment Gateway
     Database     (Razorpay/Stripe)

    Admin Panel connects to same backend APIs

------------------------------------------------------------------------

## 🗄 Database Schema (ERD)

### Users

-   `_id`, name, email, password, role (buyer/farmer/admin), address,
    phone

### Products

-   `_id`, name, category, description, price, stockQty, images\[\],
    farmerId

### Cart

-   `_id`, userId, products\[\] (productId + quantity)

### Orders

-   `_id`, userId, products\[\], totalAmount, status, paymentId,
    createdAt

### Payments

-   `_id`, userId, orderId, amount, provider, status, createdAt

------------------------------------------------------------------------

## 🔗 API Endpoints

### Authentication

-   `POST /api/auth/signup` → Register new user\
-   `POST /api/auth/login` → Login user\
-   `GET /api/auth/profile` → Get profile (JWT required)

### Products

-   `GET /api/products` → Get all products\
-   `GET /api/products/:id` → Get single product\
-   `POST /api/products` → Add product (farmer only)\
-   `PUT /api/products/:id` → Update product\
-   `DELETE /api/products/:id` → Delete product

### Cart

-   `GET /api/cart` → Get cart items\
-   `POST /api/cart` → Add to cart\
-   `PUT /api/cart/:id` → Update cart item\
-   `DELETE /api/cart/:id` → Remove item

### Orders

-   `POST /api/orders` → Place order\
-   `GET /api/orders` → Get user orders\
-   `GET /api/orders/:id` → Get order details\
-   `PUT /api/orders/:id` → Update status (admin/farmer)

### Payments

-   `POST /api/payments` → Create payment\
-   `GET /api/payments/:id` → Get payment details

### Admin

-   `GET /api/admin/dashboard` → Admin stats\
-   `GET /api/admin/orders` → All orders\
-   `PUT /api/admin/products/:id/approve` → Approve product

------------------------------------------------------------------------

## 📂 Project Folder Structure

### Frontend (React)

    src/
     ├── api/         # Axios configs
     ├── assets/      # Images
     ├── components/  # Navbar, Footer, ProductCard, etc.
     ├── pages/       # Home, Products, Cart, Checkout, Login, Signup
     ├── redux/       # Redux slices (auth, products, cart, orders)
     ├── App.js
     └── index.js

### Backend (Node + Express)

    backend/
     ├── config/       # DB connection, JWT secrets
     ├── controllers/  # Business logic
     ├── models/       # Mongoose schemas
     ├── routes/       # API routes
     ├── middleware/   # Auth & role middleware
     ├── server.js     # App entry point
     └── package.json

------------------------------------------------------------------------

## ⚡ Setup Instructions

### 1. Clone Repository

``` bash
git clone https://github.com/your-username/agri-shop.git
cd agri-shop
```

### 2. Setup Frontend

``` bash
cd frontend
npm install
npm start
```

### 3. Setup Backend

``` bash
cd backend
npm install
npm run dev
```

### 4. Environment Variables (Backend)

Create `.env` file:

    PORT=5000
    MONGO_URI=your_mongodb_atlas_url
    JWT_SECRET=your_secret_key
    RAZORPAY_KEY=your_razorpay_key
    RAZORPAY_SECRET=your_razorpay_secret

------------------------------------------------------------------------

✅ Now your **Agriculture E-commerce App** is ready to build!
