# SQL Mock Interview Series  
# Video 10 Datasets  

### Questions  
1. **Create Product and Sales Table**  
2. **Insert Sample Records into Product and Sales Table**  

---

### Dataset  

#### Product Table  

```sql
-- Create Product Table
CREATE TABLE product (
    product_id INT PRIMARY KEY,          -- Unique Product ID
    product_name VARCHAR(255),           -- Name of the Product
    price DECIMAL(10, 2)                 -- Price of the Product
);

-- Insert Sample Records
INSERT INTO product (product_id, product_name, price) VALUES
(101, 'iPhone 15', 899),
(102, 'iPhone 14', 899),
(103, 'iPhone 16', 899),
(104, 'iPhone 13', 899);

-- View Product Table
SELECT * FROM product;
```

#### Sales Table  

```sql
-- Create Sales Table
CREATE TABLE sales (
    sale_id INT PRIMARY KEY,             -- Unique Sale ID
    sale_date DATE,                      -- Date of Sale
    quantity INT,                        -- Quantity Sold
    product_id INT,                      -- Product ID (Foreign Key)
    FOREIGN KEY (product_id) REFERENCES product(product_id)
);

-- Insert Sample Records
INSERT INTO sales (sale_id, sale_date, quantity, product_id) VALUES
(1, '2024-12-06', 2, 101),
(2, '2024-12-07', 1, 102);

-- View Sales Table
SELECT * FROM sales;
```