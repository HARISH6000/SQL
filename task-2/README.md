# MySQL: Creating, Populating, Filtering, and Sorting Tables

## Objective
This task demonstrates how to create a simple table, insert data, filter records, and sort the result set using SQL queries in MySQL Workbench.

## Requirements
- Use `CREATE TABLE` to define a table with appropriate data types and constraints.
- Populate the table using `INSERT INTO` with multiple rows of sample data.
- Execute a `SELECT` query to verify the data insertion.
- Use the `WHERE` clause to filter records based on conditions.
- Apply the `ORDER BY` clause to sort the results.
- Experiment with multiple conditions using `AND`/`OR`.

## Steps

### 1. Creating the Table
We will create an `Employees`

```sql
CREATE TABLE Employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    position VARCHAR(50) NOT NULL,
    department VARCHAR(50) NOT NULL,
    salary DECIMAL(10,2) NOT NULL,
    hire_date DATE NOT NULL
);
```

### 2. Inserting Sample Data

```sql
INSERT INTO Employees (name, position, department, salary, hire_date) VALUES
('Alice Johnson', 'Software Engineer', 'IT', 75000.00, '2023-01-15'),
('Bob Smith', 'Data Analyst', 'Finance', 68000.00, '2022-11-20'),
('Charlie Brown', 'System Administrator', 'IT', 72000.00, '2023-03-10'),
('Diana Green', 'Sales Executive', 'Sales', 60000.00, '2022-12-01'),
('Ethan White', 'Marketing Manager', 'Marketing', 80000.00, '2023-02-15');
```

![View](./output/1.png)

### 3. Retrieving Data
To verify that the data was inserted correctly, execute:

```sql
SELECT * FROM Employees;
```

![View](./output/2.png)

### 4. Filtering Records
To filter employees from the IT department:

```sql
SELECT * FROM Employees WHERE department = 'IT';
```

To filter employees with a salary greater than 70,000:

```sql
SELECT * FROM Employees WHERE salary > 70000;
```

### 5. Sorting Results
To sort employees by salary in ascending order:

```sql
SELECT * FROM Employees ORDER BY salary ASC;
```

To sort employees by name in descending order:

```sql
SELECT * FROM Employees ORDER BY name DESC;
```

### 6. Using Multiple Conditions
To find employees in the IT department earning more than 70,000:

```sql
SELECT * FROM Employees WHERE department = 'IT' AND salary > 70000;
```

To find employees in either IT or Sales departments:

```sql
SELECT * FROM Employees WHERE department = 'IT' OR department = 'Sales';
```


