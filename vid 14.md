video 14


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

