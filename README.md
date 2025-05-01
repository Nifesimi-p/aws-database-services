# aws-database-services
## Basic SQL and DynamoDB Practice Guide

### Overview

This project demonstrates basic **CRUD operations** (Create, Read, Update, Delete) using:
- A **relational database** (SQL - MySQL)
- A **NoSQL database** (AWS DynamoDB)

It includes SQL query examples and a beginner-friendly DynamoDB key-value store created via the **AWS Console**.

---

## Part 1: SQL Operations (Using `employees` Table)

### Table Creation

```sql
CREATE TABLE employees (
  id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  position VARCHAR(100),
  salary DECIMAL(10,2)
);
```

###  Insert Sample Data

```sql
INSERT INTO employees (name, position, salary)
VALUES
('Ada Lovelace', 'Software Engineer', 85000.00),
('Grace Hopper', 'Backend Developer', 92000.00),
('Linus Torvalds', 'System Architect', 110000.00),
('Margaret Hamilton', 'Lead Engineer', 100000.00),
('Tim Berners-Lee', 'Web Developer', 95000.00),
('Donald Knuth', 'Algorithm Expert', 98000.00),
('Barbara Liskov', 'Computer Scientist', 105000.00),
('Alan Turing', 'Cryptanalyst', 115000.00);
```

###  Read (Select Data)

```sql
-- View all employees
SELECT * FROM employees;

-- Find a specific employee
SELECT * FROM employees WHERE name = 'Grace Hopper';
```

### Update Data

```sql
-- Update salary of a specific employee
UPDATE employees
SET salary = 95000.00
WHERE name = 'Grace Hopper';
```

### Delete Data

```sql
-- Delete employees with salary below 90,000
DELETE FROM employees
WHERE salary < 90000.00;
```

>  If you get an error like `Error Code: 1175`, disable "Safe Updates" in MySQL Workbench:
> Preferences → SQL Editor → Uncheck "Safe Updates" → Reconnect

---

##  Part 2: AWS DynamoDB (Key-Value Store)

###  Steps to Set Up in AWS Console

1. Log in to [AWS Console](https://aws.amazon.com/console/)
2. Search for **DynamoDB** and open it
3. Click **“Create table”**
   - Table name: `KeyValueStore`
   - Partition key: `Key` (Type: String)
4. Click **“Create table”**

---

### Add Items (Key-Value Pairs)

1. Go to the `KeyValueStore` table → **Items** tab → **Create item**
2. Use JSON or form view:
```json
{
  "P_Key": "name",
  "pets": "Precious Nife"
}
```

---

###  Query Items

- Go to **Query** tab
- Search with: `Key = pets`

---

###  Update Items

- Go to **Items** tab → Select item → Click **Edit**
- Change value and click **Save**

---

###  Delete Items

- Select item → Click **Actions** → Delete item

---

##  Screenshots 

###  SQL Table and Output
- ![SQL Create Result](https://github.com/Nifesimi-p/aws-database-services/blob/main/CREATE.png)
- ![SQL Update Result](https://github.com/Nifesimi-p/aws-database-services/blob/main/UPDATE.png)
- ![SQL Delete Result](https://github.com/Nifesimi-p/aws-database-services/blob/main/DELETE.png)
- ![READ/RETRIEVE](https://github.com/Nifesimi-p/aws-database-services/blob/main/RETRIEVE.png)
- ![RDS-INSTANCE](https://github.com/Nifesimi-p/aws-database-services/blob/main/RDS-INSTANCE.png)




###  DynamoDB Console
- ![DynamoDB Table Created](https://github.com/Nifesimi-p/aws-database-services/blob/main/DynamoDB1.png)
- ![DynamoDB Query Result](https://github.com/Nifesimi-p/aws-database-services/blob/main/DYNAMODB2.png)

---

##  Summary

- Practiced basic SQL operations
- Set up a DynamoDB key-value store via AWS Console
- Learned to perform Create, Read, Update, Delete operations on both systems

---

