# Product CRUD API

A simple Node.js + Express + Mongoose API implementing a `Product` model with validations, full CRUD operations, and a pre-save hook that capitalizes the product name.

## Requirements
- Node.js and npm
- MongoDB (local or cloud)

## Setup
1. Install dependencies
   ```bash
   npm install
   ```
2. Configure environment (already provided defaults)
   - `.env`
     ```
     MONGODB_URI=mongodb://localhost:27017/productDB
     PORT=3000
     ```
3. Run the server
   ```bash
   npm start
   ```

## API
- POST `/api/products`  Create a product
- GET `/api/products`   Read all products
- GET `/api/products/:id` Read one product
- PUT `/api/products/:id` Update a product
- DELETE `/api/products/:id` Delete a product

## Model validations
- name: required, max length 100, trimmed
- price: required, min 0
- category: required, one of [Electronics, Clothing, Books, Home, Other]

## Pre-save hook
Automatically capitalizes each word of `name` before saving.
