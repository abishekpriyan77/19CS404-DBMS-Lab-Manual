# Experiment 4: Aggregate Functions, Group By and Having Clause

- NAME: ABISHEIK PRIYAN V
- REG.NO: 212224230005

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
How many patients have expired insurance coverage for each insurance company?

Sample table:Insurance Table

```sql
SELECT InsuranceCompany, COUNT(*) AS TotalExpiredPatients 
FROM Insurance 
WHERE ValidityPeriod < DATE('now') 
GROUP BY InsuranceCompany;
```

**Output:**

<img width="1103" height="788" alt="image" src="https://github.com/user-attachments/assets/12130989-767a-4455-a206-53bc27c2fb9a" />


**Question 2**
---
How many doctors specialize in each medical specialty?

Sample table:Doctors Table



```sql
select Specialty, count(*) as TotalDocto
from Doctors
group by Specialty
order by Specialty;
```

**Output:**

<img width="890" height="713" alt="image" src="https://github.com/user-attachments/assets/a42c3439-2fd0-4a0a-8e9b-16bfc4e7c56d" />


**Question 3**
---
Write a SQL query to determine the number of customers who received at least one grade for their activity.

Sample table: customer

customer_id |   cust_name    |    city    | grade | salesman_id 

-------------+----------------+------------+-------+-------------

        3002 | Nick Rimando   | New York   |   100 |        5001

        3007 | Brad Davis     | New York   |   200 |        5001

        3005 | Graham Zusi    | California |   200 |        5002

```sql
select count(*) as COUNT
from customer;
```

**Output:**

<img width="642" height="385" alt="image" src="https://github.com/user-attachments/assets/bda4145d-9db3-491c-a74b-6c71fabfbc79" />


**Question 4**
---
Write a SQL query to return the total number of rows in the 'customer' table where the city is Noida.

Sample table: customer

```sql
SELECT COUNT(*) AS COUNT
FROM customer
WHERE city = 'Noida';
```

**Output:**

<img width="557" height="392" alt="image" src="https://github.com/user-attachments/assets/0db20bc0-235b-4eb2-b179-a0e16688759a" />


**Question 5**
---
Write a SQL query to find the total amount of fruits with a unit type of 'LB'.

Note: Inventory attribute contains amount of fruits
Table: fruits

name        type
----------  ----------
id          INTEGER
name        TEXT
unit        TEXT
inventory   INTEGER
price       REAL

```sql
SELECT SUM(inventory) AS total FROM fruits WHERE unit = 'LB';
```

**Output:**

<img width="461" height="387" alt="image" src="https://github.com/user-attachments/assets/f561dff1-14b2-42c7-8e2b-67a2eb2b37c0" />


**Question 6**
---
Write a SQL query to find the total number of unique cities in the customer table?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT
city        TEXT
email       TEXT
phone       INTEGER

```sql
select count(city) as unique_cities from customer;
```

**Output:**

<img width="655" height="391" alt="image" src="https://github.com/user-attachments/assets/c28e800a-9d8d-44d2-9300-a792190c5ae8" />


**Question 7**
---
Write the SQL query that achieves the grouping of data by city, calculates the average income for each city, and includes only those cities where the average income is greater than 500,000.

Sample table: employee

```sql
SELECT
  city,
  AVG(income) AS "AVG(income)"
FROM
  employee
GROUP BY
  city
HAVING
  AVG(income) > 500000;
```

**Output:**

<img width="690" height="520" alt="image" src="https://github.com/user-attachments/assets/e8a8fb21-ef0d-4ed2-8140-6bf384329649" />

**Question 8**
---
Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the average age for each group, and excludes groups where the average age is not less than 24.

Sample table: customer1

```sql
SELECT (age/5)*5 AS age_group, AVG(age)
FROM customer1
GROUP BY age_group
HAVING AVG(age) < 24;
```

**Output:**

  <img width="665" height="412" alt="image" src="https://github.com/user-attachments/assets/f4aedc71-9546-4db7-bea1-5cf79c6a7e32" />


**Question 9**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the total work hours for each date, and excludes dates where the total work hour sum is not greater than 40.

Sample table: employee1

```sql
SELECT jdate, SUM(workhour) FROM employee1 GROUP BY jdate HAVING SUM(workhour) > 40;
```

**Output:**
<img width="780" height="465" alt="image" src="https://github.com/user-attachments/assets/64d44cbd-c41a-4cf5-bedf-4290875f5994" />


**Question 10**
---
What is the average dosage prescribed for each medication?

Sample tablePrescriptions Table

```sql
select Medication,avg(Dosage) as AvgDosage from Prescriptions
group by Medication
order by Medication;
```

**Output:**

<img width="937" height="827" alt="image" src="https://github.com/user-attachments/assets/edaf428d-3d8e-431f-b79f-83564d8c13e7" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
