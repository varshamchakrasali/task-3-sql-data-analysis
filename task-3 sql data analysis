# Task-3-SQL-Data-Analysis

## 🚀 Objective
Use SQL queries to extract and analyze data from an eCommerce database.

## 🛠 Tools Used
- MySQL
- DBeaver for query execution
- Sample eCommerce database 

## 📂 Deliverables
- SQL file with queries
- Screenshots of outputs

## 📑 Key SQL Concepts Covered
- SELECT statements with WHERE, ORDER BY, GROUP BY
- Aggregate functions (SUM, AVG, COUNT)
- JOINS (INNER, LEFT, RIGHT)
- Subqueries
- Views creation
- Indexes for query optimization

sql code 

-- Create a new database
CREATE DATABASE  ecommerce_db;


-- Drop table if exists (for repeat runs)
DROP TABLE IF EXISTS orders;

-- Create orders table
CREATE TABLE orders (
    order_id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT,
    category VARCHAR(50),
    amount DECIMAL(10, 2),
    shipping_address VARCHAR(255),
    order_date DATE
);

-- Insert sample data
INSERT INTO orders (customer_id, category, amount, shipping_address, order_date) VALUES
(1, 'Electronics', 1200.00, '123 Main St', '2024-03-15'),
(2, 'Fashion', 300.00, '456 Market St', '2024-03-16'),
(3, 'Home Decor', 450.00, '789 Garden Ave', '2024-03-16'),
(4, 'Fashion', 150.00, NULL, '2024-03-17'),
(5, 'Electronics', 2200.00, '321 Lake Rd', '2024-03-17'),
(1, 'Home Decor', 800.00, '123 Main St', '2024-03-18'),
(2, 'Electronics', 500.00, NULL, '2024-03-19'),
(3, 'Fashion', 200.00, '789 Garden Ave', '2024-03-20'),
(1, 'Electronics', 700.00, '123 Main St', '2024-03-20'),
(5, 'Fashion', 1300.00, '321 Lake Rd', '2024-03-21');

-- 1. Total Sales by Category
SELECT category, SUM(amount) AS total_sales
FROM orders
GROUP BY category
ORDER BY total_sales DESC;

-- 2. Top 5 Customers by Revenue
SELECT customer_id, SUM(amount) AS revenue
FROM orders
GROUP BY customer_id
ORDER BY revenue DESC
LIMIT 5;

-- 3. Average Order Value
SELECT AVG(amount) AS avg_order_value
FROM orders;

-- 4. Orders with NULL shipping info
SELECT * FROM orders
WHERE shipping_address IS NULL;

-- 5. Creating a View: Customers with revenue > 5000
DROP VIEW IF EXISTS top_customers;
CREATE VIEW top_customers AS
SELECT customer_id, SUM(amount) AS revenue
FROM orders
GROUP BY customer_id
HAVING revenue > 5000;

-- 6. Subquery: Customers with orders > average order amount
SELECT customer_id
FROM orders
GROUP BY customer_id
HAVING SUM(amount) > (
    SELECT AVG(amount) FROM orders
);

-- 7. Optimizing Query: Creating an Index
CREATE INDEX idx_customer_id ON orders(customer_id);


output screenshots



