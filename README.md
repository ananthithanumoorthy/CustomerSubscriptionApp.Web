# Customer Subscription Web Application

## Overview
This is a simple **ASP.NET Core Web Application** built to demonstrate login, role-based authentication, 
and a Customer Subscription management module. The project includes clean API design, error handling, 
and a simple UI for testing.

---

## Features

### Authentication
- User login with **username + password**.
- Roles and permissions implemented with **ASP.NET Core Identity + Cookie Authentication**.
- Password reset functionality.

### Customer Subscription Module
- Manage subscriptions with the following fields:
  - ID
  - Customer ID
  - Customer Name
  - Subscription Name
  - Subscription Count
  - Start Date
  - End Date
  - Active (Enable/Disable)
- API Endpoints:
  - **Get Customer Subscription**
    - Input: Customer ID (mandatory), Subscription Name (optional), Start Date & End Date (optional).
    - Output: Subscription details based on filters.
  - **Subscription Management**
    - Add, update, and delete subscription records.
  - **Subscription Count Update**
    - Input: Customer ID and Subscription Name.
    - Functionality: Increment or decrement subscription count.

---

## Tech Stack
- **ASP.NET Core 8.0**
- **Entity Framework Core** (Code First + SQLite Database)
- **Bootstrap 5** (Frontend styling)
- **Cookie Authentication**
- **C# 12**

---

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/ananthithanumoorthy/CustomerSubscriptionApp.Web.git
cd CustomerSubscriptionApp
```

### 2. Database Migration
Run the following commands to apply migrations and create the database:
```bash
dotnet ef database update
```

### 3. Run the Application
```bash
dotnet run --project CustomerSubscriptionApp.Web
```
The application will start on:
- https://localhost:44352/Account/Login

### 4. Test Login Credentials
Default seeded users (from `DataSeeder.cs`):
- **Admin**
  - Username: `admin`
  - Password: `Admin@123`
- **User**
  - Username: `user`
  - Password: `User@123`

---

## Folder Structure
```
CustomerSubscriptionApp/
│── CustomerSubscriptionApp.Web/   # Main Web Project (MVC + API Controllers)
│   ├── Controllers/               # API & MVC Controllers
│   ├── Data/                      # DbContext & Seed Data
│   ├── Models/                    # Entity Models & ViewModels
│   ├── Repositories/              # Repository Pattern Implementation
│   ├── Services/                  # Business Logic Services
│   ├── Views/                     # Razor Views
│   └── Program.cs                 # Startup Configuration
│
│── README.md                      # Project Documentation
```

---

## Error Handling
- Invalid login attempts show "Invalid credentials".
- API requests return meaningful **HTTP status codes**:
  - `400 Bad Request` → Invalid input.
  - `404 Not Found` → Customer or subscription not found.
  - `500 Internal Server Error` → Unexpected server errors.

---

## Estimated Completion Time
Estimated development time: **3–4 days(2 hours per day**.

---

## Author
Developed by **[Ananthi]**
