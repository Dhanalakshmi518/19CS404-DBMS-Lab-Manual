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
<img width="798" height="367" alt="image" src="https://github.com/user-attachments/assets/6ecb6176-3aa3-4cf4-98d5-24b0f56dcbe3" />


```sql
 CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT NOT NULL,
    Price REAL CHECK (Price > 0),
    Stock INTEGER CHECK (Stock >= 0)
);
```

**Output:**

<img width="1148" height="244" alt="image" src="https://github.com/user-attachments/assets/a4cc8120-10dc-4399-ad2b-fffcd3a3a80d" />


**Question 2**
<img width="1194" height="595" alt="image" src="https://github.com/user-attachments/assets/9a026622-681f-49ae-a6db-bc82026fab01" />


```sql
ALTER TABLE customer
ADD COLUMN email VARCHAR(100);
```

**Output:**
<img width="1155" height="324" alt="image" src="https://github.com/user-attachments/assets/4fcba286-eb84-4023-86df-aaf9ef0eeb33" />


**Question 3**

<img width="1192" height="514" alt="image" src="https://github.com/user-attachments/assets/bb423110-3d29-4d65-968f-d5b3f094fc7a" />

```sql
INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (306, 'Diana Prince', 'Themyscira', NULL, NULL);

INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (307, 'Bruce Wayne', 'Wayne Manor', 'Gotham', 10007);

INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (308, 'Peter Parker', 'Queens', NULL, 11375);
```

**Output:**
<img width="1149" height="253" alt="image" src="https://github.com/user-attachments/assets/15711f6b-c75d-49ef-8678-432d932fc230" />


**Question 4**
<img width="1188" height="414" alt="image" src="https://github.com/user-attachments/assets/fee5f2d3-52e8-4bde-94a6-f365180342a9" />


```sql
CREATE TABLE Events (
    EventID   INTEGER,
    EventName TEXT,
    EventDate DATE
);
```

**Output:**

<img width="1151" height="342" alt="image" src="https://github.com/user-attachments/assets/53a2eb1d-1d99-42db-900c-11a75ff1cdb3" />


**Question 5**
<img width="1196" height="361" alt="image" src="https://github.com/user-attachments/assets/aca5f009-08d2-4bf4-b2b9-7204312b09d3" />


```sql
ALTER TABLE Student_details
ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';
```

**Output:**
<img width="1151" height="211" alt="image" src="https://github.com/user-attachments/assets/b81361b6-09e5-473d-b061-e1c10c109c96" />


**Question 6**
<img width="1181" height="462" alt="image" src="https://github.com/user-attachments/assets/d73ca10d-3d7a-444c-8f3e-038f0102a3bb" />


```sql
CREATE TABLE Reviews (
    ReviewID INTEGER,
    ProductID INTEGER,
    Rating REAL,
    ReviewText TEXT
);
```

**Output:**
<img width="1151" height="366" alt="image" src="https://github.com/user-attachments/assets/e7da8c3f-a5b0-4444-ae77-3b74e8cf829f" />


**Question 7**
<img width="991" height="412" alt="image" src="https://github.com/user-attachments/assets/7caff423-d169-4f9b-b295-dbc38de838ce" />


```sql
CREATE TABLE Orders (
    OrderID INTEGER,
    OrderDate TEXT,
    CustomerID INTEGER
);
```

**Output:**
<img width="1148" height="338" alt="image" src="https://github.com/user-attachments/assets/2088a7d0-43d7-4681-b793-c9c949253c69" />


**Question 8**
<img width="1170" height="293" alt="image" src="https://github.com/user-attachments/assets/21453c63-19b2-4cb0-b274-b734f5e23b5a" />


```sql
INSERT INTO Books (ISBN, Title, Author, Publisher, Year)
VALUES ('978-1234567890', 'Data Science Essentials', 'Jane Doe', 'TechBooks', 2024);
```

**Output:**
<img width="1154" height="202" alt="image" src="https://github.com/user-attachments/assets/216e0b1b-24be-47a5-a2db-481e2d04037b" />


**Question 9**
<img width="840" height="488" alt="image" src="https://github.com/user-attachments/assets/0ae31139-33b3-4df1-8071-69d5d504829e" />

```sql
INSERT INTO Customers(ID, NAME, AGE, ADDRESS, SALARY)
VALUES(1, 'Ramesh', 32, 'Ahmedabad', 2000);
INSERT INTO Customers(ID, NAME, AGE, ADDRESS, SALARY)
VALUES(2, 'Khilan', 25, 'Delhi', 1500);
INSERT INTO Customers(ID, NAME, AGE, ADDRESS, SALARY)
VALUES(3 , 'Kaushik', 23, 'Kota', 2000);
```

**Output:**
<img width="1151" height="248" alt="image" src="https://github.com/user-attachments/assets/03efa5ee-1f15-43cd-80d1-0f7800577a18" />


**Question 10**
<img width="1191" height="388" alt="image" src="https://github.com/user-attachments/assets/9af2dfb5-0a0e-48ee-aa2d-d3c416c8a6f8" />


```sql
CREATE TABLE Attendance(
  AttendanceID INTEGER PRIMARY KEY,
  EmployeeID INTEGER,
  AttendanceDate DATE,
  Status TEXT CHECK(Status IN ('Present','Absent','Leave')),
  FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)

);
```

**Output:**

<img width="1146" height="251" alt="image" src="https://github.com/user-attachments/assets/13ca7357-cb5a-47e1-b893-5bc46c5ed591" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
