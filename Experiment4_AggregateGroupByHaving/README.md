# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
-- What is the most common diagnosis among patients?

Sample table:MedicalRecords Table

```sql
SELECT Diagnosis, COUNT(*) AS DiagnosisCount FROM MedicalRecords
GROUP BY Diagnosis
ORDER BY DiagnosisCount DESC
LIMIT 1;
```

**Output:**

<img width="1221" height="259" alt="image" src="https://github.com/user-attachments/assets/43ed0218-44aa-49f7-89f6-47b903787a76" />


**Question 2**
---
-- Write a SQL Query to find how many medications are prescribed for each patient?

Sample table:MedicalRecords Table

```sql
SELECT PatientID, COUNT(Medications) AS AvgMedications FROM MedicalRecords
GROUP BY PatientID;
```

**Output:**

<img width="1220" height="524" alt="image" src="https://github.com/user-attachments/assets/9ddcb110-b70a-41b4-94a9-fea2a0f12838" />


**Question 3**
---
-- What is the count of male and female patients?

Sample table: Patients Table

```sql
SELECT Gender, COUNT(Gender) AS TotalPatients FROM Patients
GROUP BY Gender;
```

**Output:**

<img width="1213" height="304" alt="image" src="https://github.com/user-attachments/assets/e195d09e-d7f7-4af0-b56c-9c1bfbecfbd3" />


**Question 4**
---
-- Write a SQL query to find the total amount of fruits with a unit type of 'LB'.

Note: Inventory attribute contains amount of fruits

```sql
SELECT SUM(inventory) AS total FROM fruits
WHERE unit = 'LB';
```

**Output:**

<img width="1216" height="272" alt="image" src="https://github.com/user-attachments/assets/0707df66-47fc-493c-ab8f-8f71dc54f8b8" />


**Question 5**
---
-- Write a SQL query to find the minimum purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

```sql
SELECT MIN(purch_amt) AS MINIMUM FROM orders;
```

**Output:**

<img width="1247" height="269" alt="image" src="https://github.com/user-attachments/assets/1885e21d-c500-45a0-a4a4-bc4e21bf3bac" />


**Question 6**
---
-- Write a SQL query to determine the number of customers who received at least one grade for their activity.

Sample table: customer

customer_id |   cust_name    |    city    | grade | salesman_id 

-------------+----------------+------------+-------+-------------

        3002 | Nick Rimando   | New York   |   100 |        5001

        3007 | Brad Davis     | New York   |   200 |        5001

        3005 | Graham Zusi    | California |   200 |        5002

```sql
SELECT COUNT(*)AS COUNT FROM customer
WHERE grade >= 1;
```

**Output:**

<img width="1219" height="264" alt="image" src="https://github.com/user-attachments/assets/77494d00-f3fe-4acd-b218-f3a5e8993856" />


**Question 7**
---
-- Write a SQL query to find  how many employees work in California?

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```sql
SELECT COUNT(*) AS employees_in_california FROM employee
WHERE city = 'California';
```

**Output:**

<img width="1218" height="256" alt="image" src="https://github.com/user-attachments/assets/1af15841-de28-4a4a-bfa2-09eabb9a51d9" />


**Question 8**
---
-- Write the SQL query that accomplishes the selection of product which has lowest price in each category from the "products" table and includes only those products where the minimum price is less than 10.

Sample table: products



```sql
SELECT category_id, MIN(price) AS Price FROM products
GROUP BY category_id
HAVING price < 10;
```

**Output:**

<img width="1219" height="302" alt="image" src="https://github.com/user-attachments/assets/551178cc-33c6-4694-8835-26bb653d9484" />


**Question 9**
---
-- Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the total salary sum for each group, and excludes groups where the total salary sum is not greater than 5000.

Sample table: customer1



```sql
SELECT (age/5)*5 AS age_group, SUM(salary) FROM customer1
GROUP BY age_group
HAVING SUM(salary) > 5000;
```

**Output:**

<img width="1221" height="311" alt="image" src="https://github.com/user-attachments/assets/7ba94d8c-8e68-4bcd-986b-30d1072b4387" />


**Question 10**
---
-- Write the SQL query that accomplishes the grouping of data by age, calculates the total income for each age group, and includes only those age groups where the total income sum is greater than 1,000,000.

Sample table: employee



```sql
SELECT age, SUM(income) FROM employee
GROUP BY age
HAVING SUM(income) > 1000000;
```

**Output:**

<img width="1216" height="357" alt="image" src="https://github.com/user-attachments/assets/5499a811-0cc5-4b4d-b625-af67346dd43f" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
