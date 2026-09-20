# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
<img width="1133" height="666" alt="image" src="https://github.com/user-attachments/assets/c60fb1b9-20b5-4f77-9cfe-b62b1bbadbc9" />


```sql
select p.first_name AS patient_name,a.*
FROM PATIENTS p
INNER JOIN APPOINTMENTS a ON p.patient_id=a.patient_id;
```

**Output:**

<img width="1145" height="532" alt="image" src="https://github.com/user-attachments/assets/271b1752-527f-4b7d-8ce9-29b3afb04904" />

**Question 2**
<img width="1148" height="643" alt="image" src="https://github.com/user-attachments/assets/79b97d74-c9e5-429e-ada9-b87536011c06" />


```sql
SELECT c.*
FROM CUSTOMER c
LEFT JOIN ORDERS o
ON c.customer_id=o.customer_id
where ord_date BETWEEN '2012-08-01' AND '2012-08-30';
```

**Output:**

<img width="1148" height="457" alt="image" src="https://github.com/user-attachments/assets/963b8e44-84a0-42a8-8832-b3444aadcd3e" />


**Question 3**
<img width="1159" height="791" alt="image" src="https://github.com/user-attachments/assets/addb5fe6-ef4b-4c7b-ac29-a5341a10aca1" />


```sql
SELECT p.first_name AS patient_name,
        d.first_name AS doctor_name
fROM PATIENTS p
JOIN DOCTORS d ON p.doctor_id=d.doctor_id
where p.discharge_date IS NOT NULL;
```

**Output:**

<img width="909" height="388" alt="image" src="https://github.com/user-attachments/assets/f95e3c88-3483-447e-845d-049ef8b1e1fb" />


**Question 4**
<img width="1165" height="765" alt="image" src="https://github.com/user-attachments/assets/800e52dd-885c-4f1d-938f-e72df39ac1f1" />


```sql
SELECT s.name,c.cust_name,c.city,c.grade,c.salesman_id
FROM Salesman s
LEFT JOIN Customer c ON s.salesman_id=c.salesman_id
where c.salesman_id IN (SELECT salesman_id
FROM Customer
GROUP BY salesman_id
having COUNT(*)>1)
ORDER BY grade;
```

**Output:**

<img width="1149" height="607" alt="image" src="https://github.com/user-attachments/assets/daeb8efa-a216-4b96-b4be-82c8d2a025da" />


**Question 5**
<img width="1166" height="644" alt="image" src="https://github.com/user-attachments/assets/50dd0372-dd50-4a8a-8905-33dc2ce9c840" />

```sql
SELECT p.*
FROM PATIENTS p
INNER JOIN TEST_RESULTS t
ON p.patient_id=t.patient_id
WHERE (t.test_name='Blood Test' OR t.test_name='Blood Pressure')
AND t.result NOT LIKE '%Normal%';
```

**Output:**

<img width="1151" height="389" alt="image" src="https://github.com/user-attachments/assets/011833f0-332a-4e49-a660-e6f6363fe36a" />


**Question 6**
<img width="1168" height="658" alt="image" src="https://github.com/user-attachments/assets/ed4d6e83-900f-4946-97c5-cb79464eb409" />

```sql
SELECT p.date_of_birth,a.*
FROM PATIENTS p
INNER JOIN APPOINTMENTS a ON p.patient_id=a.patient_id
WHERE p.first_name='Alice';
```

**Output:**

<img width="1153" height="382" alt="image" src="https://github.com/user-attachments/assets/1fa4f804-a372-4c34-b9d3-0c90564916b8" />

**Question 7**
<img width="1161" height="740" alt="image" src="https://github.com/user-attachments/assets/f47005e5-1918-422b-a3b9-01797d5eb50e" />


```sql
SELECT c.cust_name,s.name
FROM Customer c
LEFT JOIN Salesman s ON c.salesman_id=s.salesman_id
where c.city=s.city;
```

**Output:**
<img width="819" height="515" alt="image" src="https://github.com/user-attachments/assets/b460f1cb-3e41-42dc-9635-980ea5520eef" />



**Question 8**
<img width="1158" height="838" alt="image" src="https://github.com/user-attachments/assets/da6b1059-3fda-4ed0-a578-ef499968c015" />

```sql
SELECT p.*,d.first_name AS doctor_name
FROM PATIENTS p
INNER JOIN DOCTORS d ON p.doctor_id=d.doctor_id;
```

**Output:**
<img width="1153" height="520" alt="image" src="https://github.com/user-attachments/assets/8b16849c-d495-4655-b3d7-6f2382204630" />

**Question 9**
<img width="1116" height="986" alt="image" src="https://github.com/user-attachments/assets/fa004a99-8a05-4c78-89b6-1c5de64dd1da" />

```sql
SELECT c.cust_name,
c.city,c.grade,s.name AS Salesman,
s.city FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
ORDER BY c.customer_id ASC;
```

**Output:**

<img width="1147" height="900" alt="image" src="https://github.com/user-attachments/assets/1afb7ad4-a893-4e9e-a257-ad7c94346e5d" />


**Question 10**
<img width="1168" height="784" alt="image" src="https://github.com/user-attachments/assets/5896693e-fb56-4fb6-b75a-22c785b9638c" />


```sql
SELECT p.first_name,s.*
FROM PATIENTS p 
INNER JOIN SURGERIES s ON p.patient_id=s.patient_id
where p.date_of_birth>'1990-01-01';
```

**Output:**

<img width="1151" height="388" alt="image" src="https://github.com/user-attachments/assets/e380850b-04df-4c0c-bec1-77617e594ff7" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
