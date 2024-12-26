# SQL Mock Interview Series

## SQL Mock Interview 2

### Questions

1. **What is the difference between a View and a Materialized View in SQL?**

2. **What is the difference between UNION and UNION ALL?**

3. **Self Join vs Cross Join:**  
   Explain the differences and provide examples for both.

4. **Self Join Query:**  
   Write an SQL query to find employees along with their manager's name and salary.

5. **Recursive CTE Query:**  
   Write an SQL query using a recursive CTE to find employees along with their manager's name and salary.

6. **Find Top Hotels by Stays:**  
   Write an SQL query to find the top 4 hotels in each month with the highest number of stays.

---

### Dataset 1: Employee and Department Tables

#### Employee Table (`emp`)
```sql
CREATE TABLE emp (
    emp_id INT PRIMARY KEY,        
    emp_name VARCHAR(100),         
    salary DECIMAL(10, 2),         
    department_id INT,             
    manager_id INT                 
);

INSERT INTO emp (emp_id, emp_name, salary, department_id, manager_id) VALUES
(1, 'Alice Johnson', 75000, 101, NULL),   
(2, 'Bob Smith', 95000, 101, 1),         
(3, 'Charlie Davis', 55000, 102, NULL),  
(4, 'Diana Prince', 85000, 102, 3),      
(5, 'Eve Adams', 40000, 103, 1),         
(6, 'Frank Taylor', 60000, NULL, 1),     
(7, 'Grace Lee', 80000, 101, 1),         
(8, 'Helen Carter', 65000, NULL, 3),      
(9, 'Ivy Brown', 87000, 102, 3),        
(10, 'Jack Wilson', 50000, 103, 1),      
(11, 'Karen White', 75000, 103, 1);
```

#### Department Table (`dept`)
```sql
CREATE TABLE dept (
    department_id INT PRIMARY KEY,     
    department_name VARCHAR(100)      
);

INSERT INTO dept (department_id, department_name) 
VALUES
(101, 'Human Resources'),
(102, 'Engineering'),
(103, 'Finance'),
(104, 'IT'),
(105, 'Marketing');
```

#### Preview Data
```sql
SELECT * FROM emp;
SELECT * FROM dept;
```

---

### Dataset 2: Hotels and Bookings Tables

#### Hotels Table
```sql
CREATE TABLE Hotels (
    hotel_id SERIAL PRIMARY KEY,
    hotel_name VARCHAR(255) NOT NULL
);

INSERT INTO Hotels (hotel_name)
VALUES 
    ('Hotel A'),
    ('Hotel B'),
    ('Hotel C'),
    ('Hotel D'),
    ('Hotel E');
```

#### Bookings Table
```sql
CREATE TABLE Bookings (
    booking_id SERIAL PRIMARY KEY,
    booking_date DATE NOT NULL,
    checkin_date DATE NOT NULL,
    hotel_id INT NOT NULL,
    FOREIGN KEY (hotel_id) REFERENCES Hotels(hotel_id)
);

INSERT INTO Bookings (booking_date, checkin_date, hotel_id)
VALUES
    ('2024-01-01', '2024-01-02', 1),
    ('2024-01-03', '2024-01-04', 2),
    ('2024-01-04', '2024-01-05', 1),
    ('2024-01-05', '2024-01-06', 3),
    ('2024-01-10', '2024-01-11', 4),
    ('2024-02-01', '2024-02-02', 1),
    ('2024-02-03', '2024-02-04', 5),
    ('2024-02-05', '2024-02-06', 2),
    ('2024-02-06', '2024-02-07', 3),
    ('2024-02-07', '2024-02-08', 1),
    ('2024-02-09', '2024-02-10', 4),
    ('2024-03-01', '2024-03-02', 3),
    ('2024-03-03', '2024-03-04', 1),
    ('2024-03-05', '2024-03-06', 2),
    ('2024-03-07', '2024-03-08', 4),
    ('2024-03-09', '2024-03-10', 5),
    ('2024-04-01', '2024-04-02', 1),
    ('2024-04-03', '2024-04-04', 2),
    ('2024-04-05', '2024-04-06', 3),
    ('2024-04-07', '2024-04-08', 4),
    ('2024-04-09', '2024-04-10', 5),
    ('2024-05-01', '2024-05-02', 1),
    ('2024-05-03', '2024-05-04', 2),
    ('2024-05-05', '2024-05-06', 3),
    ('2024-05-07', '2024-05-08', 4),
    ('2024-05-09', '2024-05-10', 5),
    ('2024-06-01', '2024-06-02', 1),
    ('2024-06-03', '2024-06-04', 2),
    ('2024-06-05', '2024-06-06', 3),
    ('2024-06-07', '2024-06-08', 4),
    ('2024-06-09', '2024-06-10', 5),
    ('2024-07-01', '2024-07-02', 1),
    ('2024-07-03', '2024-07-04', 2),
    ('2024-07-05', '2024-07-06', 3);
```

--- 

### End of Dataset
