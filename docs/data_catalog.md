# Gold Layer Data Catalog

## Overview

The Gold Layer is the business-level data representation, structured to support analytical and reporting use cases.

## 1. gold.dim_customers

**Purpose:** Stores customer details enriched with demographic and geographic data.

| Column Name | Data Type | Description |
|---|---|---|
| customer_key | INT | Surrogate key uniquely identifying each customer record in the dimension table. |
| customer_id | INT | Unique numerical identifier assigned to each customer. |
| customer_number | NVARCHAR(50) | Alphanumeric identifier representing the customer, used for tracking and referencing. |
| first_name | NVARCHAR(50) | The customer's first name, as recorded in the system. |
| last_name | NVARCHAR(50) | The customer's last name or family name. |
| country | NVARCHAR(50) | The country of residence for the customer. |
| marital_status | NVARCHAR(50) | The marital status of the customer (e.g., Married, Single). |
| gender | NVARCHAR(50) | The gender of the customer (e.g., Male, Female, n/a). |
| birthdate | DATE | The customer's date of birth, formatted as YYYY-MM-DD. |
| create_date | DATE | The date when the customer record was created in the system. |

## 2. gold.dim_products

**Purpose:** Stores product details, including category, cost, and product line information.

| Column Name | Data Type | Description |
|---|---|---|
| product_key | INT | Surrogate key uniquely identifying each product record. |
| product_id | INT | Unique identifier assigned to each product. |
| product_number | NVARCHAR(50) | Product code used to identify the product. |
| product_name | NVARCHAR(50) | Name of the product. |
| category_id | NVARCHAR(50) | Identifier of the product category. |
| category | NVARCHAR(50) | Category to which the product belongs. |
| subcategory | NVARCHAR(50) | Subcategory of the product. |
| maintenance | NVARCHAR(50) | Indicates maintenance requirements. |
| cost | INT | Cost of the product. |
| product_line | NVARCHAR(50) | Product line classification. |
| start_date | DATE | Date from which the product record is valid. |

## 3. gold.fact_sales

**Purpose:** Stores sales transaction details and connects customers and products for analytical reporting.

| Column Name | Data Type | Description |
|---|---|---|
| order_number | NVARCHAR(50) | Unique sales order number. |
| product_key | INT | Foreign key referencing the product dimension. |
| customer_key | INT | Foreign key referencing the customer dimension. |
| order_date | DATE | Date the order was placed. |
| shipping_date | DATE | Date the order was shipped. |
| due_date | DATE | Expected delivery date. |
| sales_amount | INT | Total sales amount for the transaction. |
| quantity | INT | Number of units sold. |
| price | INT | Price per unit. |
