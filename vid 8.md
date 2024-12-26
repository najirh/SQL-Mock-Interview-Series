Video 8

-- student grades
```sql
CREATE TABLE StudentGrades (
    student_id INT,
    subject VARCHAR(50),
    grade INT -- Grade out of 100
);

INSERT INTO StudentGrades VALUES
(1, 'Math', 85),
(1, 'Science', 90),
(1, 'History', 80),
(2, 'Math', 70),
(2, 'Science', 65),
(2, 'History', 75),
(3, 'Math', 95),
(3, 'Science', 85),
(3, 'History', 80),
(4, 'Math', 60),
(4, 'Science', 70),
(4, 'History', 65);
```

-- Datasets 2

-- Attendance Patterns
-- HARD

```sql
-- DATASETS
CREATE TABLE Attendance (
    student_id INT,
    attendance_date DATE,
    attendance_status VARCHAR(10)
);

INSERT INTO Attendance VALUES
(1, '2024-12-01', 'Present'),
(1, '2024-12-02', 'Absent'),
(1, '2024-12-03', 'Late'),
(1, '2024-12-04', 'Present'),
(1, '2024-12-05', 'Present'),
(2, '2024-12-01', 'Absent'),
(2, '2024-12-02', 'Absent'),
(2, '2024-12-03', 'Present'),
(2, '2024-12-04', 'Present'),
(2, '2024-12-05', 'Late'),
(3, '2024-12-01', 'Late'),
(3, '2024-12-02', 'Late'),
(3, '2024-12-03', 'Present'),
(3, '2024-12-04', 'Absent'),
(3, '2024-12-05', 'Absent');

SELECT * FROM Attendance;

```