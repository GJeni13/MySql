Project Overview
This project implements a simple e-commerce system using MySQL. It includes three main tables: customers, orders, and products. These tables are used to manage basic e-commerce data such as customer information, product listings, and order details. Additionally, an order_items table is included to normalize the database by handling the many-to-many relationship between orders and products.

Database Structure
  1.Customers Table: Stores customer information such as name, email, and address.
Columns:
id: Primary key, auto-incrementing.
name: Customer’s name.
email: Customer’s email address (unique).
address: Customer’s physical address.
  2.Products Table: Stores product details such as name, price, and description.
Columns:
id: Primary key, auto-incrementing.
name: Name of the product.
price: Price of the product.
description: Description of the product.
  3.Orders Table: Stores information about customer orders.
Columns:
id: Primary key, auto-incrementing.
customer_id: Foreign key referencing the customers table.
order_date: Timestamp of the order.
total_amount: Total amount of the order.
  4.Order Items Table: Stores details about which products are included in each order.
Columns:
id: Primary key, auto-incrementing.
order_id: Foreign key referencing the orders table.
product_id: Foreign key referencing the products table.
quantity: Quantity of each product in the order.

Key SQL Queries**
Retrieve all customers who have placed an order in the last 30 days.
Get the total amount of all orders placed by each customer.
Update the price of Product C to 45.00.
Add a new column discount to the products table.
Retrieve the top 3 products with the highest price.
Get the names of customers who have ordered Product A.
Join the orders and customers tables to retrieve the customer's name and order date for each order. 
Retrieve the orders with a total amount greater than 150.00.
Normalize the database by creating a separate table for order items and updating the orders table to reference the order_items table.
Retrieve the average total of all orders.

Explanation of Queries:
Retrieve customers with recent orders: Joins customers and orders to find distinct customers who have placed an order in the last 30 days.
Total amount by customer: Sums the total amount spent by each customer.
Update product price: Changes the price of Product C to 45.00.
Add discount column: Adds a new column for discounts in the products table.
Top 3 products: Retrieves the top three products based on price.
Customers who ordered Product A: Finds the names of customers who ordered Product A through a join.
Customer names and order dates: Retrieves names and order dates from the orders and customers tables.
Orders greater than 150.00: Selects orders where the total amount exceeds 150.00.
Normalize with order items: Creates a new order_items table to separate order details and update references.
Average total of orders: Calculates the average total amount of all orders.

Instructions to Run the Project
Create the Database:

Use the provided SQL script to create the ecommerce database and all associated tables (customers, orders, products, and order_items).
Insert Sample Data:

Run the SQL queries to insert sample data into the tables. Sample data is provided for customers, products, and orders.
Run Queries:

Use the SQL queries provided to interact with the data, such as retrieving customer details, updating product prices, and joining tables to analyze customer orders.
Database Management:

Drop tables if needed using DROP TABLE commands.
Disable safe mode temporarily if you encounter errors while updating the data.

How to Use Safe Update Mode
If you encounter errors due to MySQL’s safe update mode, you can disable it temporarily by running the following command:

sql:
SET SQL_SAFE_UPDATES = 0;
After running your updates, you can re-enable it:

sql:
SET SQL_SAFE_UPDATES = 1;

Normalization
This project implements database normalization by separating order details from the main orders table into a separate order_items table. This helps reduce redundancy and ensures a clean many-to-many relationship between orders and products.

