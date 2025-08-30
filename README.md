# Oracle_DataBase_SQL



# Oracle SQL - DDL (Data Definition Language)

## DDL Commands
- **CREATE** – Used to create database objects like tables.
- **DROP** – Deletes entire database objects permanently.
- **ALTER** – Used to modify existing database objects.
- **TRUNCATE** – Removes all rows from a table but keeps its structure.
- **RENAME** – Renames a database object.

---

## Example Queries

### SELECT Statement
```sql
SELECT * FROM SPORTS_DATA;
````

### INSERT Statement

```sql
INSERT INTO SPORTS_DATA VALUES (103, 'anjali', 'cricket', 55);
```

---

## ALTER Command

### Adding a New Column

```sql
ALTER TABLE SPORTS_DATA ADD HEIGHT NUMBER(2);
```

### Modifying a Column

```sql
ALTER TABLE SPORTS_DATA MODIFY HEIGHT NUMBER(3);
```

### Renaming a Column

```sql
ALTER TABLE SPORTS_DATA RENAME COLUMN FNAME TO FULL_NAME;
```

### Dropping a Column

```sql
ALTER TABLE SPORTS_DATA DROP COLUMN WEIGHT;
```

### Renaming a Table

```sql
ALTER TABLE SPORTS_DATA RENAME TO PLAYERS_DATA;
```

---

## DROP Command

```sql
DROP TABLE PLAYERS_DATA;
```

---

## Creating a New Table

```sql
CREATE TABLE EMPLOYEE_DATE(
    EMP_ID NUMBER(5),
    EMP_NAME VARCHAR2(50),
    EMP_SAL NUMBER(8,2), 
    EMP_ROLE VARCHAR2(250)
);
```

### Selecting Data

```sql
SELECT * FROM EMPLOYEE_DATE;
```

### Inserting Data

```sql
INSERT INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) 
VALUES (101, 'MAHESH KUMAR', 55000, 'SOFTWARE ENGINEER');

INSERT INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) 
VALUES (102, 'RAJESH', 57000, 'BACKEND ENGINEER');

INSERT INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) 
VALUES (101, 'RAMEHS KUMAR', 45000, 'FRONTEND ENGINEER');
```

---

## TRUNCATE Command

* **TRUNCATE deletes all rows from a table but keeps the table structure.**
* **Faster than DELETE.**
* **Data cannot be rolled back.**

```sql
TRUNCATE TABLE EMPLOYEE_DATE;
```

---

 These are the basic **DDL commands with examples**.


# Oracle SQL - DML (Data Manipulation Language)

## What is DML?
- **DML (Data Manipulation Language)** is used to manipulate data stored in tables.  
- It works on **rows/records** of a table.  
- DML operations can be **rolled back** or **committed** because they are transactional.  

## DML Commands
1. **INSERT** – Adds new rows into a table.  
2. **UPDATE** – Modifies existing rows in a table.  
3. **DELETE** – Removes rows from a table.  
4. **SELECT** – Retrieves data from a table.  

---

## 1. INSERT Command

### Syntax
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
````

### Example

```sql
INSERT INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE)
VALUES (106, 'SUBRAHMANYAM', 70000, 'BACKEND');
```

---

## 2. INSERT ALL Command

* Inserts **multiple rows at once** using a single statement.
* Useful for bulk inserts.

### Syntax

```sql
INSERT ALL
  INTO table_name (col1, col2, ...) VALUES (val1, val2, ...)
  INTO table_name (col1, col2, ...) VALUES (val1, val2, ...)
  INTO table_name (col1, col2, ...) VALUES (val1, val2, ...)
SELECT * FROM dual;
```

### Example

```sql
INSERT ALL
  INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) VALUES (101, 'JYOTHI', 35000, 'DEVELOPER')
  INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) VALUES (102, 'SREENU', 53000, 'HR')
  INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) VALUES (103, 'KAVYA', 58000, 'HR')
  INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) VALUES (104, 'KONDA', 30000, 'AI')
  INTO EMPLOYEE_DATE (EMP_ID, EMP_NAME, EMP_SAL, EMP_ROLE) VALUES (105, 'NARESH', 45000, 'AI')
SELECT * FROM dual;
```

---

## 3. UPDATE Command

* Updates existing row values in a table.
* Can update multiple columns at once.
* Use **WHERE clause** to target specific rows.

### Syntax

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### Example

```sql
UPDATE EMPLOYEE_DATE 
SET EMP_NAME = 'SRAVAN KIRAN', EMP_SAL = 65000, EMP_ID = 105
WHERE EMP_ROLE = 'TESTER';
```

---

## 4. DELETE Command

* Deletes rows from a table.
* Use **WHERE clause** to remove specific rows.
* If no condition is provided, **all rows** will be deleted.

### Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

### Example

```sql
DELETE FROM EMPLOYEE_DATE
WHERE EMP_ID = 105;
```

---

## 5. SELECT Command

* Retrieves rows from a table.
* You can fetch specific columns or all columns (`*`).

### Syntax

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### Example

```sql
SELECT * FROM EMPLOYEE_DATE;
```

---

## Key Points

* **INSERT** – Add new rows.
* **UPDATE** – Change existing rows.
* **DELETE** – Remove rows.
* **SELECT** – Retrieve rows.
* DML statements are **transactional** (can be rolled back or committed).

---

SQL (**Structured Query Language**) is used to manage and manipulate relational databases.
It provides commands categorized into different groups:

* **DDL** – Data Definition Language (CREATE, ALTER, DROP, TRUNCATE)
* **DML** – Data Manipulation Language (INSERT, UPDATE, DELETE, SELECT)
* **TCL** – Transaction Control Language (COMMIT, ROLLBACK, SAVEPOINT)
* **DCL** – Data Control Language (GRANT, REVOKE)
* **Operators** – Arithmetic, Comparison, Logical, Special

---

## Creating Table

```sql
CREATE TABLE employee (
    emp_id NUMBER,
    emp_name VARCHAR(240),
    emp_sal NUMBER(8,2),
    emp_role VARCHAR(250)
);
```

 Explanation:

* `emp_id` → Employee ID (Number type)
* `emp_name` → Employee Name (Text)
* `emp_sal` → Employee Salary (up to 8 digits, 2 decimals)
* `emp_role` → Employee Role

---

##  Inserting Data

```sql
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (1, 'Ravi Kumar', 50000, 'Software Engineer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (2, 'Priya Sharma', 60000, 'Senior Developer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (3, 'Amit Verma', 45000, 'UI Designer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (4, 'Sneha Reddy', 70000, 'Team Lead');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (5, 'Vikas Singh', 40000, 'Tester');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (6, 'Anjali Gupta', 80000, 'Project Manager');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (7, 'Rahul Mehta', 55000, 'Data Analyst');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (8, 'Neha Patel', 47000, 'HR Executive');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (9, 'Arjun Nair', 75000, 'DevOps Engineer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (10, 'Kavya Iyer', 52000, 'Business Analyst');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (11, 'Manish Kumar', 48000, 'Support Engineer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (12, 'Pooja Rani', 65000, 'Database Administrator');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (13, 'Sanjay Das', 42000, 'Software Engineer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (14, 'Divya Sharma', 90000, 'Product Manager');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (15, 'Nikhil Jain', 46000, 'QA Engineer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (16, 'Shreya Rao', 70000, 'Tech Lead');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (17, 'Abhishek Singh', 38000, 'Intern');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (18, 'Meena Kumari', 72000, 'System Architect');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (19, 'Kiran Kumar', 51000, 'Software Developer');
INSERT INTO employee (emp_id, emp_name, emp_sal, emp_role) VALUES (20, 'Lakshmi Menon', 58000, 'HR Manager');

```

Inserted 20 records into the `employee` table.

---

## DML Commands

### SELECT – Retrieve data

```sql
SELECT * FROM employee;
```

### INSERT – Add new record

```sql
INSERT INTO employee(emp_id, emp_name, emp_sal, emp_role)
VALUES (21, 'Maheswaram', 750000, 'Backend Developer');
```

### UPDATE – Modify data

```sql
UPDATE employee SET emp_sal = emp_sal + 5000 WHERE emp_id = 1;
```

### DELETE – Remove data

```sql
DELETE FROM employee WHERE emp_id = 5;
```

---

##  TCL Commands

### COMMIT – Save changes permanently

```sql
COMMIT;
```

### ROLLBACK – Undo uncommitted changes

```sql
ROLLBACK;
```

### SAVEPOINT – Create a checkpoint in transaction

```sql
SAVEPOINT sp1;
ROLLBACK TO sp1;
```

---

##  DCL Commands

### GRANT – Give permission

```sql
GRANT INSERT, UPDATE ON employee TO Anuradha;
```

### REVOKE – Remove permission

```sql
REVOKE INSERT, UPDATE ON employee FROM Anuradha;
```

---

##  Operators in Oracle SQL

### Arithmetic Operators

* `+` (Addition)
* `-` (Subtraction)
* `*` (Multiplication)
* `/` (Division)

Example:

```sql
SELECT emp_id, emp_name, emp_sal + 1000 AS BonusSalary
FROM employee WHERE emp_id = 14;
```

---

###  Comparison Operators

* `=` Equals
* `!=` or `<>` Not Equal
* `>` Greater than
* `<` Less than
* `>=` Greater than or Equal
* `<=` Less than or Equal

Example:

```sql
SELECT * FROM employee WHERE emp_role = 'HR Manager';
SELECT * FROM employee WHERE emp_role <> 'Data Analyst';
```

---

###  Logical Operators

* **AND** → Both conditions must be true
* **OR** → Any condition true
* **NOT** → Negates condition

Example:

```sql
SELECT * FROM employee 
WHERE emp_sal >= 550000 AND emp_role = 'Backend Developer';
```

---

###  Special Operators

####  BETWEEN

```sql
SELECT * FROM employee WHERE emp_sal BETWEEN 30000 AND 40000;
```

####  IN

```sql
SELECT * FROM employee 
WHERE emp_role IN ('Team Lead', 'Backend Developer', 'Support Engineer');
```

####  LIKE (Pattern Matching)

* `%` → Any number of characters
* `_` → Exactly one character

```sql
SELECT * FROM employee WHERE emp_name LIKE 'A%';   -- starts with A  
SELECT * FROM employee WHERE emp_name LIKE '%ar%'; -- contains 'ar'  
```

#### IS NULL

```sql
SELECT * FROM employee WHERE emp_sal IS NULL;
```

---

##  Practical Queries

 Employees with salary greater than `75000`

```sql
SELECT * FROM employee WHERE emp_sal > 75000;
```

 Employees except Backend Developer

```sql
SELECT * FROM employee WHERE NOT emp_role = 'Backend Developer';
```

 Double the salary of emp\_id = 20

```sql
SELECT emp_id, emp_name, emp_sal * 2 AS double_salary 
FROM employee WHERE emp_id = 20;
```

---

##  Summary

* **DDL** → Defines structure of tables
* **DML** → Works with data (Insert, Update, Delete, Select)
* **TCL** → Manages transactions (Commit, Rollback, Savepoint)
* **DCL** → Manages permissions (Grant, Revoke)
* **Operators** → Used in conditions and calculations

---
