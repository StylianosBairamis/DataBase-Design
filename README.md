# Database Design Project

This repository contains the design approach for a database system based on specific requirements. The report.pdf includes the Entity-Relationship (ER) diagram and the Relational diagram of the database. The SQL code is automatically generated using DBDesigner Fork.

## Contents:

1. [ER Diagram](report.pdf#page=5)
2. [Relational Diagram](report.pdf#page=10)
3. [SQL Code](sql_code.sql)

## ER Diagram

![ER Diagram](er_diagram.png)

The ER diagram provides a visual representation of the entities and their relationships within the database system.

## Relational Diagram

![Relational Diagram](relational_diagram.png)

The Relational diagram illustrates the structure of the tables and their relationships, derived from the ER diagram.

## SQL Code

```sql
-- SQL code automatically generated using DBDesigner Fork
-- Replace this code with the SQL generated by your tool

-- Example SQL code:

CREATE TABLE users (
    user_id INT PRIMARY KEY,
    username VARCHAR(50),
    email VARCHAR(100)
);

CREATE TABLE products (
    product_id INT PRIMARY KEY,
    name VARCHAR(100),
    price DECIMAL(10,2),
    description TEXT
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    user_id INT,
    order_date DATE,
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);

CREATE TABLE order_items (
    order_item_id INT PRIMARY KEY,
    order_id INT,
    product_id INT,
    quantity INT,
    FOREIGN KEY (order_id) REFERENCES orders(order_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);

-- Additional tables and constraints...
