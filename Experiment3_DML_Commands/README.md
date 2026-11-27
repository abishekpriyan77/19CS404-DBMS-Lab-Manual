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
Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id

```sql
UPDATE products
SET product_name = 'Premium Bread'
WHERE product_id = 5;
```

**Output:**
<img width="1221" height="466" alt="image" src="https://github.com/user-attachments/assets/8fd29cdc-450e-47e5-83cf-78c829ac71cc" />


**Question 2**
---
Write a SQL statement to Update the grade of all customers in Chennai city as  5. 

Customer table (customer_id,cust_name,city,grade,salesman_id)

```sql
UPDATE Customer
SET grade = 5
WHERE city = 'Chennai';
```

**Output:**

<img width="1217" height="540" alt="image" src="https://github.com/user-attachments/assets/a131285b-fa65-4662-b25f-b01adf1806d4" />

**Question 3**
---
Write a SQL statement to Update the reorder level to 20 where the quantity in stock is less than 10 and product category is 'Snacks' in the products table.

Products table

---------------
product_id
product_name
category
cost_price
sell_price
reorder_lvl
quantity
supplier_id

```sql
UPDATE products
SET reorder_lvl = 20
WHERE quantity < 10 AND category = 'Snacks';
```

**Output:**

<img width="1207" height="633" alt="image" src="https://github.com/user-attachments/assets/b023a67f-8562-421c-aa5a-58ab9b0990b8" />

**Question 4**
---
Write a SQL query to Delete customers with 'GRADE' 2 and 'CUST_NAME' starting with 'M', and whose 'PAYMENT_AMT' is less than 3000

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.0

```sql
DELETE FROM customer
WHERE GRADE = 2
AND CUST_NAME LIKE 'M%'
AND PAYMENT_AMT < 3000;
```

**Output:**

<img width="1230" height="463" alt="image" src="https://github.com/user-attachments/assets/9f972f38-ffdc-4d52-a10b-0cf333649f2e" />

**Question 5**
---
Write a SQL query to Delete All Doctors whose ID ranges from 2 to 4.

Sample table: Doctors

attributes : doctor_id, first_name, last_name, specialization
For example:

Test	Result
SELECT * FROM doctors;
doctor_id   first_name  last_name   specialization
----------  ----------  ----------  --------------
1           John        Smith       Cardiology
2           Emily       Johnson     Orthopedics
3           Michael     Brown       Pediatrics
doctor_id   first_name  last_name   specialization
----------  ----------  ----------  --------------
1           John        Smith       Cardiology

```sql
DELETE FROM doctors WHERE doctor_id BETWEEN 2 AND 4;
```

**Output:**

<img width="1222" height="906" alt="image" src="https://github.com/user-attachments/assets/1cfe65cc-e387-4272-af66-29318f442372" />

**Question 6**
---
Write a SQL query to Delete customers from 'customer' table where 'WORKING_AREA' is 'New York'.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+  
|CUST_CODE  | CUST_NAME   | CUST_CITY   | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO     | AGENT_CODE |
+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
| C00013    | Holmes      | London      | London       | UK           |     2 |     6000.00 |     5000.00 |     7000.00 |       4000.00 | BBBBBBB      | A003       |
| C00001    | Micheal     | New York    | New York     | USA          |     2 |     3000.00 |     5000.00 |     2000.00 |       6000.00 | CCCCCCC      | A008       |
| C00020    | Albert      | New York    | New York     | USA          |     3 |     5000.00 |     7000.00 |     6000.00 |       6000.00 

```sql
DELETE FROM customer
WHERE WORKING_AREA ='New York';
```

**Output:**


<img width="1221" height="860" alt="image" src="https://github.com/user-attachments/assets/5f87085d-9200-431b-9887-f3bca716a6d8" />

**Question 7**
---
Write a SQL query to categorize value1 in the Calculations table as 'High' if it is greater than 50, otherwise 'Low'.

cid         name        type        notnull     dflt_value  pk
----------  ----------  ----------  ----------  ----------  ----------
0           id          INTEGER     0                       1
1           value1      REAL        0                       0
2           value2      REAL        0                       0
3           base        INTEGER     0                       0
4           exponent    INTEGER     0                       0
5           number      REAL        0                       0
6           decimal     REAL        0                       0
 
```sql
SELECT 
id,
value1,
CASE
WHEN value1 > 50 THEN 'High'
ELSE 'Low'
END AS value_category
FROM calculations;
```

**Output:**

<img width="945" height="358" alt="image" src="https://github.com/user-attachments/assets/c81413b9-0f32-43d1-bc63-e7bb80448099" />

**Question 8**
---
Write a SQL query to retrieve the details of all customers whose ID belongs to any of the values 3007, 3008 or 3009. Return customer_id, cust_name, city, grade, and salesman_id.

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002
        
```sql
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE customer_id IN (3007,3008,3009);
```

**Output:**

<img width="1218" height="483" alt="image" src="https://github.com/user-attachments/assets/1849928e-286a-4a5e-b5ed-b98c1436ef3c" />

**Question 9**
---
Write a SQL query to find the details of those salespeople who live in cities other than Paris and Rome. Return salesman_id, name, city, commission.

Sample table: salesman

 salesman_id |    name    |   city   | commission 
-------------+------------+----------+------------
        5001 | James Hoog | New York |       0.15
        5002 | Nail Knite | Paris    |       0.13
        5005 | Pit Alex   | London   |       0.11

```sql
SELECT salesman_id,name,city,commission
FROM salesman
WHERE city NOT IN ('Paris','Rome');
```

**Output:**

<img width="1232" height="453" alt="image" src="https://github.com/user-attachments/assets/20654f32-0e72-4523-9547-933078e049c5" />

**Question 10**
---
Write a SQL query to find employees who were hired after January 1, 2020.

emp table

cid         name        type        
----------  ----------  ---------- 
0           empno       INT         
1           ename       VARCHAR(100)
2           job         VARCHAR(50)
3           mgr         INT        
4           hiredate    DATE        
5           sal         DECIMAL(10,2)  
6           comm        DECIMAL(10,2)  
7           deptno      INT         

```sql
SELECT *
FROM emp
WHERE hiredate > '2020-01-01';
```

**Output:**

<img width="1227" height="430" alt="image" src="https://github.com/user-attachments/assets/46b02a1f-655f-4265-ab39-024d43c4d9ac" />

## Screenshot of Module 2 SEB Completion Grades


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
