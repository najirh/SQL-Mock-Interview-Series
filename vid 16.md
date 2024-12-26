# SQL Mock Interview Series  
# Video 16 Datasets  

### Questions  
1. **Constraints in SQL**  
   - Explain all types of constraints (e.g., NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, CHECK, DEFAULT).  

2. **Find Products Starting with "Mi"**  
   - Write a query to find all products where the name starts with "Mi".  

3. **Find Movies with Ratings More Than 7.5 or 9.5**  
   - Write a query to find movies with a rating greater than 7.5 or 9.5.  

4. **Find the Number of Shows Released Each Year**  
   - Return the count of shows released by year, but only include years where the number of shows is more than 1.  

---

### Dataset  

```sql
-- Netflix Table Definition
CREATE TABLE netflix (
    show_id INT PRIMARY KEY,             -- Unique Show ID
    show_name VARCHAR(255),              -- Show Name
    genre VARCHAR(100),                  -- Genre (e.g., Comedy, Drama)
    rating DECIMAL(3, 1),                -- Rating (e.g., 7.5)
    release_year INT                     -- Year of release
);

-- Insert Sample Records
INSERT INTO netflix (show_id, show_name, genre, rating, release_year) VALUES
(1, 'Stranger Things', 'Sci-Fi', 8.8, 2016),
(2, 'Breaking Bad', 'Drama', 9.5, 2008),
(3, 'The Crown', 'Drama', 8.7, 2016),
(4, 'Narcos', 'Crime', 8.8, 2015),
(5, 'Money Heist', 'Action', 8.3, 2017),
(6, 'Black Mirror', 'Sci-Fi', 8.8, 2011),
(7, 'The Witcher', 'Fantasy', 8.0, 2019),
(8, 'Ozark', 'Crime', 8.4, 2017),
(9, 'Wednesday', 'Comedy', 8.4, 2022), 
(10, 'Squid Game', 'Thriller', 8.0, 2021), 
(11, 'Bridgerton', 'Drama', 8.4, 2020), 
(12, 'The Umbrella Academy', 'Sci-Fi', 8.0, 2020), 
(13, 'The Sandman', 'Fantasy', 8.0, 2022);
```
