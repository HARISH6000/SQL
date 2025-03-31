# Multi-Table JOINs

## Objective
 Combine data from two related tables using JOIN operations.

## Requirements
- Create two related tables (e.g., Customers and Orders) with a foreign key relationship.
- Write an INNER JOIN query to retrieve combined information (e.g., customer names along with their order details).
- Experiment with other types of joins such as LEFT JOIN to understand how missing matches are handled.

## Steps

### 1. Creating the Table
- Creating Customers Table

```sql
CREATE TABLE Customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE
);
```

- Creating Orders Table

```sql
CREATE TABLE Orders (
    id INT AUTO_INCREMENT PRIMARY KEY,
    customer_id INT,
    order_date DATE NOT NULL,
    amount DECIMAL(10,2) NOT NULL,
    FOREIGN KEY (customer_id) REFERENCES Customers(id)
);
```

### 2. Inserting Sample Data

- Inserting Sample Data into Customers

```sql
INSERT INTO Customers (name, email) VALUES
('Alice', 'alice@example.com'),
('Bob', 'bob@example.com'),
('Charlie', 'charlie@example.com');
```
![View](./output/1.png)

- Inserting Sample Data into Orders
```sql
INSERT INTO Orders (customer_id, order_date, amount) VALUES
(1, '2024-03-01', 150.00),
(2, '2024-03-02', 200.00),
(1, '2024-03-05', 300.00);
```
![View](./output/2.png)

### 3. INNER JOIN
Retrieve customer names with their order details

```sql
SELECT Customers.name, Orders.order_date, Orders.amount
FROM Customers
INNER JOIN Orders ON Customers.id = Orders.customer_id;
```
![View](./output/3.png)


### 4. LEFT JOIN
Retrieve all customers, even those without orders

```sql
SELECT Customers.name, Orders.order_date, Orders.amount
FROM Customers
LEFT JOIN Orders ON Customers.id = Orders.customer_id;
```
![View](./output/4.png)

