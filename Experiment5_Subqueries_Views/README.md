# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
<img width="1096" height="607" alt="image" src="https://github.com/user-attachments/assets/854c5668-a38f-45c2-901b-75e42b8456bc" />


```sql
SELECT * FROM Employee
where age< ( SELECT AVG(AGE) FROM Employee WHERE income>1000000);
```

**Output:**
<img width="1140" height="369" alt="image" src="https://github.com/user-attachments/assets/809b9d50-179a-458f-9a34-ff1ab226d79f" />


**Question 2**
<img width="1076" height="676" alt="image" src="https://github.com/user-attachments/assets/ecf25545-b180-49a9-afae-26ea1cf6f8b2" />


```sql
SELECT commission
from salesman
where salesman_id IN (SELECT salesman_id
from customer
where city='Paris');

```

**Output:**

<img width="543" height="312" alt="image" src="https://github.com/user-attachments/assets/df09ede1-63ff-4ce6-910d-699764670c16" />

**Question 3**
<img width="1020" height="539" alt="image" src="https://github.com/user-attachments/assets/654cd054-fa40-4778-baf9-ab720ae0646e" />

```sql
SELECT * FROM customer
where city<>(SELECT city FROM customer where id=(select max(id) from customer));
```

**Output:**

<img width="1151" height="466" alt="image" src="https://github.com/user-attachments/assets/6a4e0cbb-d096-417d-a850-95cad3570cd5" />


**Question 4**
<img width="961" height="658" alt="image" src="https://github.com/user-attachments/assets/652e2877-014d-44d5-9a44-18a98b5e28b9" />


```sql
select * from CUSTOMERS
WHERE salary<2500;
```

**Output:**

<img width="1148" height="437" alt="image" src="https://github.com/user-attachments/assets/dafb8c35-fe63-4e59-8405-a1e8567fc636" />

**Question 5**
<img width="976" height="493" alt="image" src="https://github.com/user-attachments/assets/4da865a6-7aba-4fe4-83ac-f6ac477c894e" />


```sql
select medication_id,medication_name,dosage
from Medications
where dosage=(select min(dosage) from Medications);
```

**Output:**

<img width="938" height="388" alt="image" src="https://github.com/user-attachments/assets/c7a8c15a-84fe-4b67-bdbb-4568fbbb80ba" />


**Question 6**
<img width="988" height="726" alt="image" src="https://github.com/user-attachments/assets/bf9d4178-73b9-4b1d-84c1-9a93df19249f" />

```sql
select * from customer
where customer_id=(select salesman_id-2001
from salesman
where name='Mc Lyon');
```

**Output:**

<img width="1149" height="287" alt="image" src="https://github.com/user-attachments/assets/9b39397a-2dc2-4126-b502-e7e3bb633fee" />


**Question 7**
<img width="1110" height="451" alt="image" src="https://github.com/user-attachments/assets/e9d8c7b0-b0a0-4cb8-9eaa-9e1e1f3ebac1" />


```sql
select department_id,department_name
from Departments
where length(department_name)>(select AVG(LENGTH(department_name)) from Departments);
```

**Output:**
<img width="582" height="377" alt="image" src="https://github.com/user-attachments/assets/c1dcc3a4-eb04-4cae-82c8-73be119b5a97" />

**Question 8**
<img width="1071" height="640" alt="image" src="https://github.com/user-attachments/assets/40825173-291d-48c9-bd76-c4696550d0fb" />


```sql
select * from CUSTOMERS
WHERE ADDRESS='Delhi' and AGE <30
ORDER BY ID;
```


**Output:**
<img width="1148" height="342" alt="image" src="https://github.com/user-attachments/assets/06999328-919f-40f0-9661-6ec179ee3e15" />


**Question 9**
<img width="1033" height="741" alt="image" src="https://github.com/user-attachments/assets/843240f5-6a06-446b-9095-2471a2638650" />


```sql
SELECT * FROM CUSTOMERS
WHERE SALARY>1500;
```

**Output:**

<img width="1150" height="590" alt="image" src="https://github.com/user-attachments/assets/02cecaa4-a345-4a67-af2d-92188915e2a0" />


**Question 10**
<img width="986" height="669" alt="image" src="https://github.com/user-attachments/assets/36a003ac-7b40-4f3f-a3bd-f6055e8ff177" />

```sql
SELECT * FROM CUSTOMERS
WHERE SALARY>4500;
```

**Output:**

<img width="1145" height="419" alt="image" src="https://github.com/user-attachments/assets/2f194d02-2e6b-4fb3-8658-f0c6ec099728" />

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
