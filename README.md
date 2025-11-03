# 🎟️ Eventy Backend

The **Eventy Backend** is a microservices-based architecture that powers the Eventy mobile application, providing secure, scalable APIs for buying and reselling event tickets.

---

## 🚧 Project Status

This backend system is currently under active development.  
Some services and features described below are planned or partially implemented.

---

## 🌍 What Is Eventy Backend?

Eventy Backend is the server-side infrastructure that supports the Eventy mobile application. Built on a **microservices architecture**, it ensures scalability, maintainability, and separation of concerns across different business domains.

The backend handles:
- **User authentication and authorization** with Keycloak integration
- **Event management** and discovery
- **Ticket inventory** and sales processing
- **Secure transactions** and payment processing
- **User interactions** including messaging, reviews, and reports
- **Admin moderation** and platform safety

---

## 🏗️ Architecture Overview

### Microservices Architecture

The Eventy backend follows a microservices pattern with the following services:

```
┌─────────────────┐
│   API Gateway   │  ← Single entry point for all client requests
└────────┬────────┘
         │
    ┌────┴────┬────────┬─────────┬──────────────┐
    │         │        │         │              │
┌───▼───┐ ┌──▼───┐ ┌──▼────┐ ┌──▼─────────┐ ┌─▼──────────┐
│ Users │ │Events│ │Tickets│ │Transactions│ │Interactions│
└───┬───┘ └──┬───┘ └──┬────┘ └──┬─────────┘ └─┬──────────┘
    │        │        │         │              │
    └────────┴────────┴─────────┴──────────────┘
                      │
              ┌───────▼────────┐
              │    Keycloak    │  ← Authentication & Identity Management
              └────────────────┘
```

---

## 🔧 Microservices

### 🔐 Authentication Service (Keycloak)
Handles user authentication and session management.

**Responsibilities:**
- User login/logout
- JWT token generation and validation
- Password encryption and verification
- Session management
- OAuth integration (planned)

---

### 👥 Users Service
Manages user profiles and account information.

**Features:**
- User profile creation and management
- Account status management
- Wallet balance tracking
- Role-based access control (user, admin)
- Personal information management

---

### 🎪 Events Service
Manages events, categories, types, and user favorites.

**Features:**
- Event catalog management
- Event categorization and typing
- Advanced search and filtering
- Favorite events tracking
- Event status monitoring

---

### 🎫 Tickets Service
Manages ticket inventory, listings, and availability.

**Features:**
- Ticket listing creation
- Inventory management
- Seat and section assignment
- QR code and barcode generation
- Ticket status tracking
- Multiple ticket types support

---

### 💳 Transactions Service
Handles payment processing, transaction records, and financial operations.

**Features:**
- Secure payment processing
- Transaction history management
- Platform fee calculation
- Refund processing
- Payment receipt generation
- Multiple payment methods support

**Payment Integration:**
- Stripe (primary)
- PayPal (planned)

---

### 💬 Interactions Service
Manages user communications, reviews, and reports.

**Features:**
- Direct messaging between users
- User rating and review system
- Comprehensive reporting system
- Report status tracking
- Admin moderation tools

---

## 🔒 Security Features

### Authentication & Authorization
- **Keycloak Integration:** Industry-standard identity management
- **JWT Tokens:** Secure, stateless authentication
- **Role-Based Access Control (RBAC):** User and admin roles
- **Password Encryption:** Bcrypt hashing for passwords

### Transaction Security
- **PCI Compliance:** Secure payment processing
- **Encrypted Communications:** HTTPS/TLS for all API calls
- **Token-Based Payments:** No direct storage of payment credentials
- **Audit Logging:** Complete transaction history

### Data Protection
- **Input Validation:** Protection against injection attacks
- **Data Sanitization:** XSS prevention
- **Rate Limiting:** DDoS protection
- **Secure File Uploads:** Validated and scanned uploads

---

## 🛠️ Technology Stack

### Backend Framework
- **Java Spring Boot** - Microservices framework
- **Spring Cloud** - Service discovery and configuration
- **Spring Security** - Authentication and authorization

### Databases
- **PostgreSQL** - Primary relational database
- **Redis** - Caching and session management (planned)

### Authentication
- **Keycloak** - Identity and access management

### Payment Processing
- **Stripe API** - Payment gateway integration

### API Documentation
- **Swagger/OpenAPI** - API documentation and testing

### Containerization
- **Docker** - Container platform
- **Docker Compose** - Local development orchestration

---

## 👥 Admin Capabilities

Administrators have access to:
- **User Management:** Suspend, delete, or modify user accounts
- **Content Moderation:** Review and remove fraudulent listings
- **Report Management:** Handle user reports and disputes
- **Transaction Oversight:** Monitor and manage payments and refunds
- **Platform Analytics:** View usage statistics and metrics

---

## 🤝 Contributing

This project is part of an academic development effort.  
Contributions and feedback are welcome for educational purposes.

---

## 📄 License

© 2025 Eventy. All rights reserved.