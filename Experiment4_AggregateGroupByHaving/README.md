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
<img width="865" height="462" alt="image" src="https://github.com/user-attachments/assets/f40fe76c-7b17-43c2-9c35-d806da16554c" />


```sql
select name,max(income)
from employee
where city='California';

```

**Output:**

<img width="686" height="286" alt="image" src="https://github.com/user-attachments/assets/9bbe7c06-6bc7-49f5-b6ca-98b7ae917ed2" />

**Question 2**
<img width="986" height="487" alt="image" src="https://github.com/user-attachments/assets/2cd70db5-d28c-4d51-9ae5-2df9abed88ba" />


```sql
select count(*) AS COUNT
from customer
where city<>'Noida';
```

**Output:**
<img width="586" height="302" alt="image" src="https://github.com/user-attachments/assets/807abdf9-0e0c-48e1-845c-7f83d422313e" />


**Question 3**
<img width="951" height="493" alt="image" src="https://github.com/user-attachments/assets/c90b2ce7-7dae-4bec-9391-fda8a8255f98" />


```sql
select count(*) AS COUNT
from customer
where city='Noida';
```

**Output:**

<img width="490" height="291" alt="image" src="https://github.com/user-attachments/assets/3db8c4f5-945e-408f-9553-b9ce641d8c89" />


**Question 4**
<img width="1033" height="577" alt="image" src="https://github.com/user-attachments/assets/c420bd30-13d7-454f-bf87-8c645e010181" />

```sql
select Specialty ,
       COUNT(*) AS TotalDocto
from Doctors
group by specialty;
```

**Output:**

<img width="902" height="649" alt="image" src="https://github.com/user-attachments/assets/c5d449e8-6c2a-4875-b514-169c861e5f42" />


**Question 5**
<img width="675" height="607" alt="image" src="https://github.com/user-attachments/assets/5d45597e-0082-436a-8e10-ebd2e936031c" />


```sql
-select PatientID,
       COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY PatientID;
```

**Output:**

<img width="869" height="609" alt="image" src="https://github.com/user-attachments/assets/5af72aa9-78ed-49c2-9aa4-0c8567a2ffa9" />


**Question 6**
<img width="971" height="569" alt="image" src="https://github.com/user-attachments/assets/012a1a20-a388-4ab6-b673-8ec5255b07aa" />

```sql
select Frequency,
        Count(*) AS TotalPrescriptions
from prescriptions
group by Frequency;
```

**Output:**

<img width="957" height="514" alt="image" src="https://github.com/user-attachments/assets/f2039df9-606a-4bc6-9328-36a83d9b6361" />

**Question 7**
<img width="1159" height="473" alt="image" src="https://github.com/user-attachments/assets/74f4acef-5f9a-45d7-913a-b10c06795509" />

```sql
select category_id,
       AVG(Price)
from products
group by category_id
having AVG(Price) BETWEEN 10 AND 15;

```

**Output:**
<img width="700" height="308" alt="image" src="https://github.com/user-attachments/assets/400d931e-3717-4aa0-9e3b-8c8c48e3c153" />



**Question 8**
<img width="1142" height="592" alt="image" src="https://github.com/user-attachments/assets/915ffeae-3ed3-497e-8122-edf114cc14de" />


```sql
select (age/5)*5 AS age_group,MAX(salary)
FROM customer1
group by age_group
having max(salary)>8000;
```

**Output:**

<img width="688" height="327" alt="image" src="https://github.com/user-attachments/assets/a6406762-4ca8-4464-bd1b-b62c0eca1d16" />


**Question 9**
<img width="1181" height="533" alt="image" src="https://github.com/user-attachments/assets/40336f78-6ff7-4b48-b86b-6504649ae1a0" />

```sql
select age,MIN(income) AS Income
from employee
group by age
having MIN(income)<1000000;
```

**Output:**

<img width="697" height="406" alt="image" src="https://github.com/user-attachments/assets/f814eaf4-7d18-44d3-b450-689e4b4b05b6" />

**Question 10**
<img width="1160" height="501" alt="image" src="https://github.com/user-attachments/assets/ceaae6d1-2b77-4850-ac9f-7fa61e1c5696" />

```sql
select jdate,MIN(workhour)
from employee1
group by jdate
having MIN(workhour)<10;
```

**Output:**

<img width="777" height="405" alt="image" src="https://github.com/user-attachments/assets/2243a4a3-3fd3-4d72-9c4a-42a3cbff4a76" />
**Result:**
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
