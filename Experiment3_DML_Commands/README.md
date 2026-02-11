# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
-- Write a SQL statement to change salary of employee to 8000 whose Employee ID is 105, if the existing salary is less than 5000.

```sql
-- UPDATE Employees
SET SALARY = 8000
WHERE EMPLOYEE_ID = 105 AND SALARY < 5000;
```

**Output:**

<img width="1186" height="234" alt="image" src="https://github.com/user-attachments/assets/afb829e0-4db3-47b6-8568-53283e53506d" />


**Question 2**
---
-- Write a SQL statement to Increase the salary by 500 and email as 'updated' for employees with job ID 'SA_REP' and commission percentage greater than 0.15

```sql
-- UPDATE Employees
SET SALARY = SALARY + 500, EMAIL = 'updated'
WHERE JOB_ID = 'SA_REP' AND commission_pct > 0.15;
```

**Output:**

<img width="1189" height="517" alt="image" src="https://github.com/user-attachments/assets/873924b8-918e-4e3c-a7dd-3b709c58340d" />


**Question 3**
---
-- Update the reorder level to 40 pieces for all products belonging to the 'Grocery' category in the products table.

```sql
-- UPDATE PRODUCTS
SET reorder_lvl = 40
WHERE category = 'Grocery';
```

**Output:**

<img width="1175" height="393" alt="image" src="https://github.com/user-attachments/assets/d91e9204-6656-49e5-815d-259619b1d9fe" />


**Question 4**
---
-- Write a SQL statement to Increase the selling price by 15% in the products table where quantity in stock is less than 50 and supplier ID is 10.

```sql
-- UPDATE Products
SET sell_price = sell_price*1.15
WHERE quantity < 50 AND supplier_id = 10;
```

**Output:**

<img width="1187" height="481" alt="image" src="https://github.com/user-attachments/assets/d97c91f6-e2be-4487-8bb2-038e8cb55200" />


**Question 5**
---
-- Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

```sql
-- UPDATE Products
SET product_name = 'Premium Bread'
WHERE product_id = 5;
```

**Output:**

<img width="1175" height="393" alt="image" src="https://github.com/user-attachments/assets/7002c828-3bba-4d49-a134-a7fe7ecd8fc4" />


**Question 6**
---
-- Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' has exactly 6 characters.

```sql
-- DELETE FROM Customer
WHERE LENGTH(CUST_NAME) = 6;
```

**Output:**

<img width="1185" height="732" alt="image" src="https://github.com/user-attachments/assets/247b87b5-6d81-4bfc-bed1-4540019edaf4" />


**Question 7**
---
-- Write a SQL query to Delete All Doctors with a NULL Specialization

```sql
-- DELETE FROM Doctors
WHERE specialization IS NULL;
```

**Output:**

<img width="1237" height="900" alt="image" src="https://github.com/user-attachments/assets/ae23178f-87b2-4133-812d-68ab3de38727" />


**Question 8**
---
-- Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' contains the substring 'Holmes'.

```sql
-- DELETE FROM Customer
WHERE CUST_NAME LIKE '%Holmes%';
```

**Output:**

<img width="1186" height="526" alt="image" src="https://github.com/user-attachments/assets/bfe5a1f8-7d90-4389-842c-d8f033f3b597" />


**Question 9**
---
-- Write a SQL query to Delete All Doctors with a NULL Last Name

```sql
-- DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="1184" height="705" alt="image" src="https://github.com/user-attachments/assets/6f7fbc00-1ee3-456c-8003-c24fe9ce03b1" />


**Question 10**
---
-- PWrite a SQL query to Delete all Doctors whose Specialization is either 'Pediatrics' or 'Cardiology' and Last Name is Brown.

```sql
-- DELETE FROM Doctors
WHERE (specialization = 'Pediatrics' OR specialization = 'Cardiology') AND last_name = 'Brown';
```

**Output:**

<img width="1159" height="825" alt="image" src="https://github.com/user-attachments/assets/722e4181-5550-4bdc-9ae0-125d636a57ac" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
