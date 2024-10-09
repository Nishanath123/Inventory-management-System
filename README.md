# Inventory Management System

## Overview

The Inventory Management System is a backend API built using Django Rest Framework (DRF) with PostgreSQL, Redis caching, and JWT authentication. The system allows users to perform CRUD operations on inventory items, ensuring secure and efficient management of inventory data.

## Features

- User registration and login with JWT authentication.
- CRUD operations for inventory items:
  - Create a new inventory item.
  - Retrieve a specific inventory item by ID.
  - Update an existing inventory item.
  - Delete an inventory item.
- Caching of frequently accessed items using Redis for improved performance.
- Comprehensive logging of API activities.

## Technologies Used

- Django
- Django Rest Framework
- PostgreSQL
- Redis
- JSON Web Tokens (JWT)

## Installation

### Prerequisites

- Python 3.x
- PostgreSQL
- Redis

### Steps

### 1. Create a virtual environment:
   using the below command
   --> python -m venv venv
   --> source venv/bin/activate 

### 2. Install dependencies:
   pip install -r requirements.txt

### 3. Set up the database:
   ---> Create a PostgreSQL database and user.
   ---> Update the DATABASES settings in settings.py with your database credentials.
    
### 4. Run migrations 
   ---> python manage.py makemigrations
   ---> python manage.py migrate

### 6. Start the Redis server (if not already running):
   ---> redis-server
### 7. Run the server:
   ----> python manage.py runserver


### API Endpoints

### 1.User Registration
      POST /register/
### Request Body :
{
  "username": "your_username",
  "password": "your_password"
}

### Response: Success message on registration.

### 2.User Login
      POST /login/
### Request Body:
{
  "username": "your_username",
  "password": "your_password"
}
### Response: Access and refresh tokens

 ### 3.Create Item:
       POST /items/
### Request Body:
{
  "name": "Item Name",
  "description": "Item Description",
  "quantity": 10,
  "price": 99.99
}

### 4. Get Item:
       GET /items/<item_id>/

### 5. Update Item:
       PUT /items/update/<item_id>/

### Request Body: (only updated fields)
{
  "name": "Updated Item Name",
  "description": "Updated Description",
  "quantity": 20,
  "price": 89.99
}

### 6. Delete Item:
       DELETE /items/delete/<item_id>/

### Logging:
API activity is logged to a file named debug.log. You can check this file for any errors or important information related to the API operations.




   

