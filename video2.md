```markdown
# SQL Mock Interview Series

Welcome to the **SQL Mock Interview Series**, designed to help you prepare for real-world SQL interview scenarios with a mix of theoretical questions and practical exercises.

---

## Video - 01

🎥 **Video Link**: [Watch on YouTube](#)

### Questions:

1. **What is the difference between `UNION` and `UNION ALL`?**

2. **Count the number of employees in the `emp` table.**
   - Write an SQL query to count the total number of employees.

3. **Find employees whose salary is greater than their managers.**
   - Write an SQL query to identify employees earning more than their managers.

---

## Dataset 1: Employee and Department Tables

### **Employee Table (`emp`)**

The `emp` table stores details about employees, including their ID, name, salary, department, and manager.

```sql
CREATE TABLE emp (
    emp_id INT PRIMARY KEY,        -- Employee ID
    emp_name VARCHAR(100),         -- Employee Name
    salary DECIMAL(10, 2),         -- Employee Salary
    department_id INT,             -- Department ID
    manager_id INT                 -- Manager ID
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

### **Department Table (`dept`)**

The `dept` table contains information about various departments.

```sql
CREATE TABLE dept (
    department_id INT PRIMARY KEY,     -- Department ID
    department_name VARCHAR(100)      -- Department Name
);

INSERT INTO dept (department_id, department_name) 
VALUES
(101, 'Human Resources'),
(102, 'Engineering'),
(103, 'Finance'),
(104, 'IT'),
(105, 'Marketing');
```

### **Preview Data**

- **Employee Table:**
  ```sql
  SELECT * FROM emp;
  ```

- **Department Table:**
  ```sql
  SELECT * FROM dept;
  ```

---

## Practice SQL Queries

### Question 1: Difference between `UNION` and `UNION ALL`
- `UNION` combines the result of two queries and removes duplicate rows.
- `UNION ALL` combines the result of two queries but includes all duplicate rows.

### Question 2: Count the Number of Employees
```sql
SELECT COUNT(*) AS employee_count FROM emp;
```

### Question 3: Find Employees with Salary Greater than Their Managers
```sql
SELECT e.emp_name, e.salary, m.emp_name AS manager_name, m.salary AS manager_salary
FROM emp e
LEFT JOIN emp m ON e.manager_id = m.emp_id
WHERE e.salary > m.salary;
```

---

### Stay Tuned
More videos and questions will be added to the series. Practice regularly to master SQL for interviews!
