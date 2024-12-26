# SQL Mock Interview Series

## Video - 03

🎥 **Video Link**: [Watch on YouTube](#)

---

### Questions Covered

1. **Difference between `NULL` and "NULL"?**
   - Understand the distinction between the `NULL` value (absence of a value) and the string "NULL".

2. **Difference between `AND` and `OR` Operators in SQL?**
   - Explore how these logical operators impact query results.

3. **Difference between `CROSS JOIN` and `LEFT JOIN`?**
   - Understand when to use these joins and their outcomes.

4. **Difference between `ROW_NUMBER()`, `RANK()`, and `DENSE_RANK()`?**
   - Learn the differences and use cases of these window functions.

5. **Do we need a Primary Key in 3rd Normal Form (3NF)?**
   - Understand the role of primary keys in maintaining 3NF.

6. **Find Customers Who Have Not Bought Anything in the Last 6 Months** (Two approaches).
   - Write queries to identify customers with no orders in the last six months.

7. **Write an SQL Query to Get the Second-Highest Salary Using a Subquery?**
   - Find the second-highest salary using efficient subquery techniques.

---

## Datasets Used

### **Orders Table (`orders`)**

The `orders` table contains details about customer purchases.

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,         -- Order ID
    customer_id INT,                  -- Customer ID
    order_date DATE,                  -- Order Date
    total_amount DECIMAL(10, 2),      -- Order Total Amount
    states VARCHAR(50),               -- Region
    category VARCHAR(50)              -- Category
);

INSERT INTO orders (order_id, customer_id, order_date, total_amount, states, category) VALUES
(1, 1, '2024-11-15', 500.00, 'Maharashtra', 'Electronics'),
(2, 2, '2024-10-10', 1200.00, 'Karnataka', 'Furniture'),
(3, 3, '2024-09-25', 300.00, 'Tamil Nadu', 'Books'),
(4, 4, '2024-06-05', 1500.00, 'Delhi', 'Clothing'),
(5, 1, '2023-12-12', 700.00, 'Kerala', 'Electronics'),
(6, 2, '2024-11-20', 800.00, 'West Bengal', 'Home Appliances'),
(7, 3, '2023-05-10', 600.00, 'Rajasthan', 'Furniture'),
(8, 5, '2024-07-15', 450.00, 'Gujarat', 'Books'),
(9, 6, '2024-01-25', 1000.00, 'Punjab', 'Electronics'), 
(10, 7, '2024-03-10', 550.00, 'Uttar Pradesh', 'Clothing');
```

### **Customers Table (`customers`)**

The `customers` table holds information about customers.

```sql
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,         -- Customer ID
    customer_name VARCHAR(100),          -- Customer Name
    email VARCHAR(100),                  -- Email Address
    phone VARCHAR(15)                    -- Phone Number
);

INSERT INTO customers (customer_id, customer_name, email, phone) VALUES
(1, 'Alice Johnson', 'alice@example.com', '1234567890'),
(2, 'Bob Smith', 'bob@example.com', '2345678901'),
(3, 'Charlie Davis', 'charlie@example.com', '3456789012'),
(4, 'Diana Prince', 'diana@example.com', '4567890123'),
(5, 'Eve Adams', 'eve@example.com', '5678901234'),
(6, 'Frank Taylor', 'frank@example.com', '6789012345'), 
(7, 'Grace Lee', 'grace@example.com', '7890133456'),
(8, 'Sam', 'grace@example.com', '9890123456'),
(9, 'Alex', 'grace@example.com', '8890123456');
```

---

### Practical Exercises

#### **Question 6: Customers Who Have Not Bought Anything in the Last 6 Months**

- **Approach 1: Using `NOT IN`**
```sql
SELECT c.customer_id, c.customer_name
FROM customers c
WHERE c.customer_id NOT IN (
    SELECT DISTINCT customer_id
    FROM orders
    WHERE order_date > DATE_ADD(CURDATE(), INTERVAL -6 MONTH)
);
```

- **Approach 2: Using `LEFT JOIN`**
```sql
SELECT c.customer_id, c.customer_name
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id 
    AND o.order_date > DATE_ADD(CURDATE(), INTERVAL -6 MONTH)
WHERE o.order_id IS NULL;
```

---

### **Question 7: Second-Highest Salary**

- Find the second-highest salary using a subquery:
```sql
SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
);


