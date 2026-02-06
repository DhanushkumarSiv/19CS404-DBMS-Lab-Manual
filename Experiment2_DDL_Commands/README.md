# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- Paste Question 1 here

```sql
-- create a table named jobs including columns job_id, job_title, min_salary and max_salary, and make sure that, the default value for job_title is blank and min_salary is 8000 and max_salary is NULL will be entered automatically at the time of insertion if no value assigned for the specified columns.
```

**Output:**


<img width="1181" height="323" alt="image" src="https://github.com/user-attachments/assets/3898f3b9-81d7-49fe-9a43-bad7496cebd2" />




**Question 2**
---
-- Paste Question 2 here

```sql
-- Write an SQL query to add a new column salary of type INTEGER to the Employees table, with a CHECK constraint that ensures the value in this column is greater than 0.
```

**Output:**


<img width="1189" height="274" alt="image" src="https://github.com/user-attachments/assets/ea2d8ae0-3a45-4cae-b20b-564c276f2845" />




**Question 3**
---
-- Paste Question 3 here

```sql
-- Create a table named ProjectAssignments with the following constraints:
AssignmentID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
ProjectID as INTEGER should be a foreign key referencing Projects(ProjectID).
AssignmentDate as DATE should be NOT NULL.
```

**Output:**


<img width="1183" height="267" alt="image" src="https://github.com/user-attachments/assets/f78ecb34-5c33-478c-95f2-add318586268" />




**Question 4**
---
-- Paste Question 4 here

```sql
-- Create a table named Products with the following constraints:

ProductID should be the primary key.
ProductName should be NOT NULL.
Price is of real datatype and should be greater than 0.
Stock is of integer datatype and should be greater than or equal to 0.
```

**Output:**


<img width="1187" height="263" alt="image" src="https://github.com/user-attachments/assets/a6c0c771-68ed-49d1-a25a-202e5a054af1" />




**Question 5**
---
-- Paste Question 5 here

```sql
-- Write a SQL query to add birth_date attribute as timestamp (datatype) in the table customer 

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002
```

**Output:**


<img width="1186" height="352" alt="image" src="https://github.com/user-attachments/assets/2bc72d15-3276-48d7-8f81-bc54a204b578" />




**Question 6**
---
-- Paste Question 6 here

```sql
-- Insert all employees from Former_employees into Employee

Table attributes are EmployeeID, Name, Department, Salary
```

**Output:**


<img width="1184" height="259" alt="image" src="https://github.com/user-attachments/assets/9a439e08-75d3-4576-8682-b64de5725d35" />



**Question 7**
---
-- Paste Question 7 here

```sql
--In the Student_details table, insert a student record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

RollNo      Name            Gender      Subject      MARKS
----------  ------------    ----------  ----------   ----------
205         Olivia Green    F
207         Liam Smith      M           Mathematics  85
208         Sophia Johnson  F           Science
```

**Output:**


<img width="1183" height="275" alt="image" src="https://github.com/user-attachments/assets/47f7f309-b39a-4557-8579-4044f11c8042" />




**Question 8**
---
-- Paste Question 8 here

```sql
-- Create a table named Orders with the following constraints:
OrderID as INTEGER should be the primary key.
OrderDate as DATE should be not NULL.
CustomerID as INTEGER should be a foreign key referencing Customers(CustomerID).
```

**Output:**


<img width="1179" height="257" alt="image" src="https://github.com/user-attachments/assets/633c7e8a-1749-4319-affe-e9e0a6d8fa99" />



**Question 9**
---
-- Paste Question 9 here

```sql
-- Insert a new product with ProductID 101, Name Laptop, Category Electronics, Price 1500, and Stock 50 into the Products table.
```

**Output:**

<img width="1206" height="219" alt="image" src="https://github.com/user-attachments/assets/52a68070-11fb-4666-bbb1-61e56a8ccd15" />


**Question 10**
---
-- Paste Question 10 here

```sql
-- Create a table named Employees with the following columns:

EmployeeID as INTEGER
FirstName as TEXT
LastName as TEXT
HireDate as DATE
```

**Output:**

<img width="1184" height="301" alt="image" src="https://github.com/user-attachments/assets/754e555f-e24b-4a11-831e-7d097c317a98" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
