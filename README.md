# SQL-Tech-Gadget-Store
<p> <b>✨ TASK ✨</b></p>

**1. String Manipulation**: Can you extract just the domain name (e.g., "gmail.com") from the email_address and list the top 3 most common email providers among these 40 users?

**2. Date Math**: Calculate the number of days between each user's signup_date and their very first purchase timestamp in the sales table.

**3. Complex Math & JOIN:** Write a query that calculates the absolute total profit (Formula: (unit_price * (1 - discount_applied) - unit_cost) * quantity) for the entire "LAP" (Laptop) category.

**4. Advanced Aggregation:** Find the top 5 users who bought the highest total quantity of items, and display their full name alongside the total quantity. Ensure the list only includes users who bought more than 3 items in total.

``` sql
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    sku VARCHAR(20), 
    product_name VARCHAR(100),
    unit_price DECIMAL(10, 2),
    unit_cost DECIMAL(10, 2) 
);

CREATE TABLE users (
    user_id INT PRIMARY KEY,
    full_name VARCHAR(100), 
    email_address VARCHAR(100), 
    signup_date DATE 
);

CREATE TABLE sales (
    sale_id INT PRIMARY KEY,
    user_id INT,
    product_id INT,
    sale_timestamp DATETIME, 
    quantity INT,
    discount_applied DECIMAL(4, 2),
    FOREIGN KEY (user_id) REFERENCES users(user_id),
    FOREIGN KEY (product_id) REFERENCES products(product_id)
);
```
**✌🏼 THE DATASET OVERVIEW ✌🏼**
<p> 👇🏼 The products table </p>

| product_id | sku | product_name | unit_price | unit_cost |
| :--- | :--- | :--- | :--- | :--- |
| 1 | LAP-X1-BLK | Laptop Pro X1 | 1200.00 | 800.000 |
| 2 | PHO-Z9-SLV | Smartphone Z9 | 800.00 | 10.00 |
| 3 |TAB-M4-WHT | Tablet M4 | 400.00 | 250.00 |
| 4 | ACC-M1-BLK| Wireless Mouse | 25.00 | 10.00 |
| 5 | ACC-K1-RGB | Mech Keyboard | 85.00 | 40.00 |

