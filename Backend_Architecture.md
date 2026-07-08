# Miscurin Backend Architecture

Version: 1.0

Status: Active Development


# 1. Backend Purpose

The Miscurin backend is the central business engine responsible for:

- Customer management
- Product management
- Orders
- Payments
- Inventory
- Staff operations
- Analytics
- Security


# 2. Backend Architecture Principle

The backend must be:

- Scalable
- Secure
- Modular
- Maintainable
- Mobile-ready


Architecture Style:

API-first architecture


# 3. Technology Direction


Backend Framework:

NestJS (Node.js)


Database:

PostgreSQL


Authentication:

Supabase Authentication


Storage:

Cloud Storage


API Communication:

REST API initially

Future:

GraphQL where required


# 4. Backend Modules


# Authentication Module


Responsibilities:

- User registration
- Login
- Password management
- Session management
- Role verification


Supports:

- Customers
- Staff
- Founders


---

# User Management Module


Responsibilities:

- Customer profiles
- User preferences
- Account status
- Customer history


---

# Product Module


Responsibilities:

- Product creation
- Product updates
- Categories
- Collections
- Variants
- Pricing


Access:

Product team with permission control


---

# Inventory Module


Responsibilities:

- Stock tracking
- Warehouse management
- Stock alerts
- Inventory movement


Example:

Product sold

↓

Inventory decreases automatically


---

# Cart Module


Responsibilities:

- Shopping cart
- Saved items
- Cart calculations


---

# Order Management Module


Responsibilities:

Complete order lifecycle.


Flow:


Customer Purchase

↓

Order Created

↓

Payment Verified

↓

Inventory Reserved

↓

Warehouse Processing

↓

Shipping

↓

Delivery


---

# Payment Module


Responsibilities:

- Payment processing
- Transaction verification
- Refund processing
- Payment history


---

# Shipping Module


Responsibilities:

- Delivery calculation
- Tracking
- Courier integration
- Delivery updates


---

# Notification Module


Supports:


Email

SMS

WhatsApp

Push Notifications


Examples:

Order confirmation

Shipping update

Delivery confirmation


---

# Review Module


Responsibilities:

- Product reviews
- Ratings
- Moderation


---

# Marketing Module


Responsibilities:

- Coupons
- Campaigns
- Promotions
- Customer segmentation


---

# CMS Module


Responsibilities:

Manage website content.


Examples:

- Homepage banners
- Blog posts
- Brand stories
- Lookbooks


---

# Analytics Module


Tracks:


Sales

Customers

Products

Marketing performance

Website behavior


---

# Staff & Permission Module


Responsibilities:


Department management

Role management

Permission control

Approval workflows


Example:


Product Assistant

↓

Product Manager Approval

↓

Publish Product


---

# Security Module


Responsibilities:


- Access control
- Activity logging
- Suspicious activity detection
- Data protection


---

# 5. Backend Communication Flow


Customer Website

↓

API Gateway

↓

Backend Services

↓

Database


Admin Dashboard

↓

Same API Layer

↓

Backend Services


Mobile App Future

↓

Same API Layer

↓

Backend Services


# 6. Background Processing


The system should support background jobs.


Examples:


Send email

↓

Process payment

↓

Generate reports

↓

Update analytics


# 7. Scalability Requirements


The backend should support:


Phase 1:

Small launch


Phase 2:

Growing customer base


Phase 3:

Global expansion


Future support:

- Multiple servers
- Microservices migration
- Cloud scaling


# 8. Development Principle


Business logic must stay in the backend.

Frontend applications should only communicate through APIs.
