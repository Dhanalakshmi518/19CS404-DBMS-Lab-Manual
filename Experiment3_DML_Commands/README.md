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
<img width="1050" height="490" alt="image" src="https://github.com/user-attachments/assets/15986be5-d4d3-40c6-8e01-59661b41c04e" />


```sql
update suppliers
set address='58 Lakeview, Magnolia'
where supplier_id=5;
```

**Output:**

<img width="1149" height="370" alt="image" src="https://github.com/user-attachments/assets/614b8021-555e-4d52-9c6b-07e5f36feb17" />


**Question 2**
<img width="1193" height="561" alt="image" src="https://github.com/user-attachments/assets/88c29ab1-1b25-45cd-a6e6-0fd432cc99e8" />


```sql
SELECT *
FROM orders
WHERE NOT (
        ord_date = '2012-08-17'
        OR (customer_id > 3005 AND purch_amt < 1000)
      );
```

**Output:**

<img width="1150" height="783" alt="image" src="https://github.com/user-attachments/assets/b4dd2693-db4b-4a3f-8aea-13bbe798ac7c" />

**Question 3**
<img width="1198" height="495" alt="image" src="https://github.com/user-attachments/assets/dc9f194e-f1b1-478d-96e2-b41a22ac3d83" />


```sql
delete from customer
where CUST_CITY <> 'New York' and OUTSTANDING_AMT>5000;
```

**Output:**

<img width="1152" height="573" alt="image" src="https://github.com/user-attachments/assets/0c425af4-e644-4d4d-b378-bb41022027fa" />


**Question 4**
<img width="1194" height="521" alt="image" src="https://github.com/user-attachments/assets/689f87ca-89de-4b01-a4cf-edb25e30f410" />


```sql
UPDATE products
SET reorder_lvl = 20
WHERE quantity < 10
AND category = 'Snacks';
```

**Output:**
<img width="1148" height="548" alt="image" src="https://github.com/user-attachments/assets/01eaec7a-69c7-451d-b021-9a24fdd51707" />


**Question 5**
<img width="1192" height="590" alt="image" src="https://github.com/user-attachments/assets/3e648f92-3730-48d8-b8b3-990ab98cc283" />


```sql
DELETE FROM customer
WHERE WORKING_AREA = 'New York';
```

**Output:**
<img width="1152" height="763" alt="image" src="https://github.com/user-attachments/assets/116547cc-cba9-471c-a77f-f868dc28b33f" />


**Question 6**
<img width="1196" height="735" alt="image" src="https://github.com/user-attachments/assets/c0c71db6-684b-4885-9244-4232e950a37c" />


```sql
UPDATE employees
SET salary = salary + 500,
    email = 'updated'
WHERE job_id = 'SA_REP'
  AND commission_pct > 0.15;
```

**Output:**
<img width="1145" height="495" alt="image" src="https://github.com/user-attachments/assets/059a70b1-07e9-4f27-9c95-f4c88438f827" />


**Question 7**
<img width="896" height="427" alt="image" src="https://github.com/user-attachments/assets/1f9b19c8-8a06-47aa-965f-fb9da4883ede" />

```sql
SELECT CategoryName, Description
FROM Categories
ORDER BY CategoryName;
```

**Output:**

<img width="1154" height="524" alt="image" src="https://github.com/user-attachments/assets/faaeb385-a56b-4d73-bc30-b4fc47143968" />

**Question 8**
<img width="1078" height="701" alt="image" src="https://github.com/user-attachments/assets/033bff2b-2a93-4960-948f-1736e7df33d9" />


```sql
SELECT 
    ename,
    CAST((julianday('2024-08-30') - julianday(hiredate)) / 365.25 AS INTEGER) AS Tenure
FROM emp;
```

**Output:**

<img width="912" height="350" alt="image" src="https://github.com/user-attachments/assets/61bdb10e-3ded-4c44-9fec-0d720d45f4e0" />


**Question 9**
<img width="1094" height="583" alt="image" src="https://github.com/user-attachments/assets/519f7d0f-4ac8-452f-9b06-e6b4cfe3acfd" />

```sql
SELECT 
    product_id,
    original_price,
    discount_percentage,
    tax_rate,
    (original_price * (1 - discount_percentage) * (1 + tax_rate)) AS final_price
FROM Products;
```

**Output:**

<img width="1148" height="257" alt="image" src="https://github.com/user-attachments/assets/a30bf9f8-9841-4a70-9251-cd3f515dec9d" />


**Question 10**
<img width="906" height="525" alt="image" src="https://github.com/user-attachments/assets/8fc76390-7fcf-4df7-804f-c196bc65d838" />


```sql
SELECT SUBSTR(EmpLname, 1, 4)
FROM EmployeeInfo;
```

**Output:**

<img width="1023" height="302" alt="image" src="https://github.com/user-attachments/assets/22ade738-186b-4ed5-9ca8-d4c9d602da65" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
