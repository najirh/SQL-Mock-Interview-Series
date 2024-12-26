video 10
```sql
-- Step 1: Create the cinema hall table
CREATE TABLE cinema_hall (
    id INT PRIMARY KEY,
    status INT CHECK (status IN (0, 1)) -- 0: Available, 1: Booked
);

-- Step 2: Insert data into the table
INSERT INTO cinema_hall (id, status) VALUES
(1, 0),
(2, 1), 
(3, 1),
(4, 0), 
(5, 0), 
(6, 0), 
(7, 1);

SELECT * FROM cinema_hall;
```

# Datasets 2
```sql

CREATE TABLE ProductPricing (
    product_id INT,
    price_date DATE,
    discount_percentage INT -- Discount percentage on that day (0 if none)
);

INSERT INTO ProductPricing VALUES
(101, '2024-12-01', 10),
(101, '2024-12-02', 15),
(101, '2024-12-03', 20),
(101, '2024-12-04', 0),
(102, '2024-12-01', 0),
(102, '2024-12-02', 5),
(102, '2024-12-03', 10),
(102, '2024-12-04', 10),
(103, '2024-12-01', 30),
(103, '2024-12-02', 25),
(103, '2024-12-03', 20),
(103, '2024-12-04', 20);

```