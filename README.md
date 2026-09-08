# Laravel Microservices

A Laravel-based Microservices architecture designed to build scalable, maintainable, and independently deployable services.

## 🚀 Overview

This project follows a Microservices Architecture where different business functionalities are separated into independent Laravel services.

Each service can have:

- Its own codebase
- Its own database
- Its own API
- Independent deployment
- Independent scaling

## 🏗️ Project Structure

```text
laravel-microservices/
│
├── api-gateway/
│   └── Laravel Application
│
├── auth-service/
│   └── Authentication & User Management
│
├── product-service/
│   └── Product Management
│
├── order-service/
│   └── Order Management
│
├── payment-service/
│   └── Payment Management
│
├── notification-service/
│   └── Email / Notification Management
│
└── README.md
```

## 🧩 Services

### API Gateway

The API Gateway acts as the main entry point for clients.

Responsibilities:

- Request routing
- Authentication
- API access control
- Communication with internal services

### Auth Service

Handles authentication and user-related operations.

Features:

- User registration
- Login
- Logout
- Token authentication
- User management

### Product Service

Handles product-related operations.

Features:

- Create product
- Update product
- Delete product
- Product listing
- Product details

### Order Service

Handles order processing.

Features:

- Create order
- Order management
- Order status
- Order history

### Payment Service

Handles payment-related operations.

Features:

- Payment processing
- Payment status
- Transaction management

### Notification Service

Handles application notifications.

Features:

- Email notifications
- Order notifications
- Payment notifications

## 🛠️ Technologies

- PHP
- Laravel
- MySQL
- REST API
- Laravel Sanctum / Passport
- Docker
- Redis
- RabbitMQ / Message Queue
- Git & GitHub

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/laravel-microservices.git
```

Go to the project:

```bash
cd laravel-microservices
```

Each service should be configured separately.

Example:

```bash
cd auth-service
```

Install dependencies:

```bash
composer install
```

Copy environment file:

```bash
cp .env.example .env
```

Generate application key:

```bash
php artisan key:generate
```

Configure your database inside `.env`.

Example:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=auth_service
DB_USERNAME=root
DB_PASSWORD=
```

Run migrations:

```bash
php artisan migrate
```

Start the service:

```bash
php artisan serve
```

## 🔐 Environment Variables

Each service should have its own `.env` file.

Example:

```env
APP_NAME=AuthService
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost:8001

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=auth_service
DB_USERNAME=root
DB_PASSWORD=
```

## 🌐 Example Service Ports

```text
API Gateway          http://localhost:8000
Auth Service         http://localhost:8001
Product Service      http://localhost:8002
Order Service        http://localhost:8003
Payment Service      http://localhost:8004
Notification Service http://localhost:8005
```

## 🔄 Microservice Communication

Services can communicate through REST APIs or message queues.

Example:

```text
Client
   │
   ▼
API Gateway
   │
   ├──► Auth Service
   │
   ├──► Product Service
   │
   ├──► Order Service
   │
   └──► Payment Service
```

For asynchronous communication:

```text
Order Service
      │
      ▼
 Message Queue
      │
      ├──► Payment Service
      │
      └──► Notification Service
```

## 🐳 Docker

Build containers:

```bash
docker compose build
```

Start services:

```bash
docker compose up -d
```

Check running containers:

```bash
docker compose ps
```

View logs:

```bash
docker compose logs -f
```

Stop services:

```bash
docker compose down
```

## 🧪 Testing

Run Laravel tests:

```bash
php artisan test
```

Or:

```bash
./vendor/bin/phpunit
```

## 📦 Useful Laravel Commands

Clear application cache:

```bash
php artisan optimize:clear
```

Run migrations:

```bash
php artisan migrate
```

Rollback migrations:

```bash
php artisan migrate:rollback
```

Create controller:

```bash
php artisan make:controller UserController
```

Create model and migration:

```bash
php artisan make:model Product -m
```

Create API controller:

```bash
php artisan make:controller ProductController --api
```

Create request:

```bash
php artisan make:request StoreProductRequest
```

List routes:

```bash
php artisan route:list
```

## 🔀 Git Workflow

Create a feature branch:

```bash
git checkout -b feature/auth-service
```

Check changes:

```bash
git status
```

Add changes:

```bash
git add .
```

Commit:

```bash
git commit -m "Add authentication service"
```

Push branch:

```bash
git push -u origin feature/auth-service
```

After completing the feature, create a Pull Request on GitHub.

## 📁 Recommended Git Structure

```text
laravel-microservices/
├── api-gateway/
├── auth-service/
├── product-service/
├── order-service/
├── payment-service/
├── notification-service/
├── docker-compose.yml
├── .gitignore
└── README.md
```

## 🔒 Security

Do not commit `.env` files.

Make sure `.gitignore` contains:

```gitignore
.env
/vendor/
/node_modules/
storage/*.key
```

Never expose:

- Database passwords
- API keys
- JWT secrets
- Application secrets
- Payment credentials

## 📌 Future Improvements

- [ ] API Gateway
- [ ] Authentication Service
- [ ] Product Service
- [ ] Order Service
- [ ] Payment Service
- [ ] Notification Service
- [ ] Redis integration
- [ ] RabbitMQ integration
- [ ] Docker Compose
- [ ] Centralized logging
- [ ] API documentation
- [ ] Automated CI/CD
- [ ] Kubernetes deployment
