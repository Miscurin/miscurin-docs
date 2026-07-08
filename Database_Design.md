# Miscurin Database Design

Version: 1.0

Status: Active Development


# 1. Database Philosophy

Miscurin requires a scalable, secure, and flexible database structure.

The database must support:

- Customer commerce
- Product management
- Inventory
- Orders
- Payments
- Staff operations
- Analytics
- Global expansion


# 2. Database Technology

Primary Database:

PostgreSQL


Managed Platform:

Supabase


Database Principles:

- Data integrity
- Security
- Scalability
- Clear relationships
- Audit tracking


# 3. Core Database Modules


# User Management


## Users Table

Stores all platform users.


Fields:

- user_id
- name
- email
- phone
- password_reference
- account_status
- created_at
- updated_at


User Types:

- Customer
- Founder
- Staff


---

# Customer Management


## Customer Profiles

Stores customer information.


Fields:

- customer_id
- user_id
- date_of_birth
- gender
- preferences
- loyalty_points
- customer_level


## Addresses


Stores customer addresses.


Fields:

- address_id
- customer_id
- country
- city
- postal_code
- address_details


---

# Product Management


## Products


Stores product information.


Fields:

- product_id
- product_name
- description
- category_id
- collection_id
- brand
- status
- created_at


## Product Variants


Handles different versions.


Examples:

Black T-shirt
Size M


Fields:

- variant_id
- product_id
- size
- color
- SKU
- price


## Product Media


Stores:

- Images
- Videos


Fields:

- media_id
- product_id
- media_type
- URL


---

# Category Management


## Categories


Examples:

- Men
- Women
- Accessories


Fields:

- category_id
- name
- description


---

# Inventory Management


## Inventory


Tracks stock.


Fields:

- inventory_id
- variant_id
- warehouse_id
- quantity
- reserved_quantity


## Warehouses


Future support for multiple locations.


Fields:

- warehouse_id
- name
- location


---

# Shopping System


## Cart


Stores active shopping carts.


Fields:

- cart_id
- customer_id
- created_at


## Cart Items


Fields:

- cart_item_id
- cart_id
- product_variant_id
- quantity


---

# Order Management


## Orders


Main purchase record.


Fields:

- order_id
- customer_id
- status
- total_amount
- payment_status
- shipping_status
- created_at


Order Status:


Pending

↓

Confirmed

↓

Processing

↓

Packed

↓

Shipped

↓

Delivered


---

## Order Items


Stores purchased products.


Fields:

- order_item_id
- order_id
- product_variant_id
- quantity
- price


---

# Payment Management


## Payments


Fields:

- payment_id
- order_id
- payment_method
- transaction_id
- amount
- status


---

# Returns Management


## Returns


Fields:

- return_id
- order_id
- reason
- status
- refund_status


---

# Review System


## Reviews


Fields:

- review_id
- customer_id
- product_id
- rating
- comment
- status


---

# Marketing System


## Coupons


Fields:

- coupon_id
- code
- discount_type
- value
- expiry


## Campaigns


Fields:

- campaign_id
- name
- start_date
- end_date


---

# Staff Management


## Employees


Fields:

- employee_id
- user_id
- department_id
- role_id


## Departments


Examples:

- Product
- Marketing
- Finance
- HR
- Support


## Roles


Examples:

- Product Manager
- Product Assistant


## Permissions


Controls access.


Fields:

- permission_id
- role_id
- action


---

# Security & Audit


## Activity Logs


Tracks important actions.


Examples:

- Price changed
- Product deleted
- Refund approved


Fields:

- log_id
- user_id
- action
- timestamp


# Future Database Support


The architecture should support:


- Multiple countries
- Multiple currencies
- Multiple warehouses
- Mobile applications
- AI recommendations
- Loyalty programs
- Physical stores
