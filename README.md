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

 Double the salary of emp_id = 20

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

# SQL Functions in SQL\*Plus

Functions in SQL are **predefined operations** that can be performed on data. They help in data manipulation, transformation, and analysis.

SQL functions are mainly categorized into two types:

1. **Scalar Functions (Single Row Functions):**

   * Operate on a single row and return a single result for each row.
2. **Aggregate Functions (Multiple Row Functions):**

   * Operate on a group of rows and return a single summarized result.

---

##  Scalar Functions (Single Row Functions)

### 1. String Functions

#### **UPPER()**

Converts lowercase letters to uppercase.

```sql
SELECT UPPER(EMP_NAME)
FROM EMPLOYEE;
```

**Explanation:** If `EMP_NAME = 'anuradha'`, the result will be `ANURADHA`.

---

#### **LOWER()**

Converts uppercase letters to lowercase.

```sql
SELECT LOWER(EMP_ROLE)
FROM EMPLOYEE;
```

**Explanation:** If `EMP_ROLE = 'MANAGER'`, the result will be `manager`.

---

#### **INITCAP()**

Capitalizes the first letter of each word.

```sql
SELECT INITCAP('anuradha') AS formatted_name
FROM dual;

SELECT INITCAP(EMP_NAME)
FROM employee;
```

**Explanation:** `'anuradha'` becomes `'Anuradha'`.

---

#### **SUBSTR()**

Extracts a substring from the main string.

**Syntax:**

```sql
SUBSTR(string, starting_position, length)
```

```sql
SELECT SUBSTR('PADAMATA ANURADHA', 1, 8) AS SUR_NAME,
       SUBSTR('PADAMATA ANURADHA', 9, 17) AS FIRST_NAME
FROM dual;
```

**Output:**

* SUR\_NAME = `PADAMATA`
* FIRST\_NAME = `ANURADHA`

---

#### **LENGTH()**

Counts the number of characters in a string.

```sql
SELECT LENGTH(EMP_NAME) AS EMPLOYEE_NAME_LENGTH
FROM EMPLOYEE;
```

**Explanation:** If `EMP_NAME = 'RAHUL'`, the result will be `5`.

---

#### **INSTR()**

Finds the position of a substring within a string.

**Syntax:**

```sql
INSTR(string, substring)
```

```sql
SELECT INSTR('ORACLE DATA BASE', 'maheswaram')
FROM dual;
```

**Explanation:** Returns `0` if the substring is not found.

---

### 2. Number Functions

#### **ROUND()**

Rounds a number to the specified decimal places.

```sql
SELECT ROUND(637.98632767, 3)
FROM dual;
```

**Output:** `637.986`

---

#### **MOD()**

Returns the remainder of a division.

```sql
SELECT MOD(678, 81)
FROM dual;
```

**Output:** `30`

---

### 3. Date Functions

#### **SYSDATE**

Returns the current system date and time.

```sql
SELECT SYSDATE
FROM dual;
```

---

#### **ADD\_MONTHS()**

Adds a number of months to a date.

```sql
SELECT ADD_MONTHS(SYSDATE, 2)
FROM dual;
```

**Explanation:** Returns today’s date plus 2 months.

---

#### **NEXT\_DAY()**

Finds the next occurrence of a specified day after the given date.

```sql
SELECT NEXT_DAY(SYSDATE, 'MONDAY')
FROM dual;
```

**Explanation:** Returns the date of the next Monday after today.

---

#### **MONTHS\_BETWEEN()**

Finds the number of months between two dates.

```sql
SELECT MONTHS_BETWEEN(SYSDATE, DATE '2026-12-12')
FROM dual;
```

**Explanation:** Returns the difference in months between the current date and December 12, 2026.

---

##  Aggregate Functions (Multiple Row Functions)

### **COUNT()**

Counts the number of rows in a table.

```sql
SELECT COUNT(*)
FROM EMPLOYEE;
```

---

### **MAX()**

Finds the maximum value in a column.

```sql
SELECT MAX(EMP_SAL) AS HIGHEST_SALARY
FROM EMPLOYEE;
```

---

### **MIN()**

Finds the minimum value in a column.

```sql
SELECT MIN(EMP_SAL) AS LOWEST_SALARY
FROM EMPLOYEE;
```

---

### **SUM()**

Calculates the total sum of values in a column.

```sql
SELECT SUM(EMP_SAL) AS TOTAL_SALARY_OF_ALL_EMPLOYEES
FROM EMPLOYEE;
```

---

### **AVG()**

Calculates the average value of a column.

```sql
SELECT AVG(EMP_SAL) AS AVERAGE_SALARY
FROM EMPLOYEE;
```

---

## Summary

* **Scalar functions** work on each row and return individual results (e.g., `UPPER()`, `ROUND()`, `SYSDATE`).
* **Aggregate functions** work on multiple rows and return one summarized result (e.g., `MAX()`, `AVG()`, `SUM()`).
* These functions make SQL queries more powerful by allowing **data formatting, calculation, and aggregation**.


# Constraints in SQL

Constraints in SQL are rules applied to table columns to ensure **accuracy, reliability, and integrity** of the data stored in the database. They restrict the type of data that can be stored and maintain relationships between tables.

---

## Types of Constraints

1. **Column-level constraints** → Applied only to a single column.
2. **Table-level constraints** → Applied to multiple columns in a table.

---

## Domain Constraints

Domain constraints restrict the values that can be stored in a column. These include:

* **NOT NULL** → Ensures a column cannot have a `NULL` value.
* **CHECK** → Ensures that all values in a column satisfy a condition.
* **DEFAULT** → Provides a default value if no value is specified.

### Syntax

```sql
CREATE TABLE table_name (
    column_name data_type CONSTRAINT_NAME CONSTRAINT_TYPE,
    ...
);
```

### Example

```sql
CREATE TABLE STUDENT (
    roll_no NUMBER NOT NULL,
    std_name VARCHAR(240) NOT NULL,
    age NUMBER CHECK (age >=18),
    gender CHAR(1) DEFAULT 'M'
);
SELECT * FROM STUDENT;

INSERT INTO STUDENT(ROLL_NO, STD_NAME, AGE, GENDER)
VALUES(101, 'ARHA', 19,'F');

INSERT INTO STUDENT(ROLL_NO, STD_NAME, AGE, GENDER)
VALUES(102, 'SUHA', 20,'F');

INSERT INTO STUDENT(ROLL_NO, STD_NAME, AGE, GENDER)
VALUES(104, 'MAHESWARAM', 20,'M');
```

 **Explanation**:

* `NOT NULL` ensures roll\_no and std\_name cannot be empty.
* `CHECK (age >= 18)` ensures student must be at least 18 years old.
* `DEFAULT 'M'` sets gender to **M** if no value is provided.

---

## CHECK Constraint

The **CHECK constraint** ensures that values inserted into a column meet a specific condition.

### Syntax

```sql
column_name data_type CHECK (condition)
```

### Example

```sql
CREATE TABLE EMP_DETAILS(
    EMP_ID NUMBER PRIMARY KEY,
    EMP_SAL NUMBER CHECK (EMP_SAL > 0)
);
SELECT * FROM EMP_DETAILS;

INSERT INTO EMP_DETAILS VALUES(101, 5000); -- VALID
INSERT INTO EMP_DETAILS VALUES(101, -5000); -- ERROR
```

 **Explanation**:

* `EMP_SAL` must always be greater than 0.
* Inserting negative salary will throw an error.

---

## Entity Constraints

Entity constraints ensure **uniqueness** and **identification** of rows.

* **PRIMARY KEY** → Combination of `UNIQUE` + `NOT NULL`. It uniquely identifies each record in a table.
* **UNIQUE** → Prevents duplicate values but allows one `NULL` value.

### Syntax

```sql
CREATE TABLE table_name (
    column_name data_type PRIMARY KEY,
    column_name data_type UNIQUE
);
```

### Example

```sql
CREATE TABLE department(
    dep_id NUMBER PRIMARY KEY,
    dep_name VARCHAR(100) UNIQUE
);

INSERT INTO department VALUES(1,'DEV');
INSERT INTO department VALUES(2,'DEV'); -- Error: Duplicate value not allowed
```

 **Explanation**:

* `dep_id` is a primary key, so it must be unique and not null.
* `dep_name` is unique, so duplicate values are not allowed.

---

## Referential Constraints (Foreign Key)

The **FOREIGN KEY** constraint maintains relationships between tables. It ensures that a value in one table exists in another.

### Syntax

```sql
CONSTRAINT constraint_name FOREIGN KEY (column_name)
REFERENCES parent_table(parent_column)
```

### Example

```sql
CREATE TABLE ZOMATOCUSTOMER(
    CUST_ID NUMBER PRIMARY KEY,
    CUST_NAME VARCHAR(50) NOT NULL ,
    PHONE VARCHAR(15) UNIQUE,
    EMIAL VARCHAR(100) UNIQUE ,
    ADDRESS VARCHAR(500) NOT NULL
);
INSERT INTO ZOMATOCUSTOMER VALUES(1,'ANURADHA','7569399294','EXAMPLE@GMAIL.COM','MTM');
SELECT * FROM ZOMATOCUSTOMER;

CREATE TABLE ZOMATO_DELIVERY_BOY(
    DELIVERY_ID NUMBER PRIMARY KEY,
    DELIVERY_NAME VARCHAR(200) NOT NULL,
    PHONE VARCHAR(15) UNIQUE,
    CUST_ID NUMBER,

    CONSTRAINT FK_CUSTOMER FOREIGN KEY (CUST_ID) REFERENCES ZOMATOCUSTOMER(CUST_ID)
);

INSERT INTO ZOMATO_DELIVERY_BOY VALUES(104, 'VINAY','893283291',1);
SELECT * FROM ZOMATO_DELIVERY_BOY;
```

 **Explanation**:

* `ZOMATOCUSTOMER` is the parent table.
* `ZOMATO_DELIVERY_BOY` references the `CUST_ID` from parent table.
* If we try to insert a delivery boy with a customer ID that does not exist, it will throw an error.

---

## Deferrable Constraints

Deferrable constraints allow **postponing the checking of constraints** until the end of the transaction (`COMMIT`).

* **NOT DEFERRABLE** (default): Constraint is checked immediately.
* **DEFERRABLE**: Constraint can be deferred and checked later.
* **INITIALLY IMMEDIATE**: Constraint is checked immediately unless deferred.
* **INITIALLY DEFERRED**: Constraint is checked only at commit.

### Syntax

```sql
CONSTRAINT constraint_name FOREIGN KEY (column_name)
REFERENCES parent_table(parent_column)
DEFERRABLE INITIALLY DEFERRED;
```

### Example

```sql
CREATE TABLE CUSTOMER_SWIGGY(
    CUST_ID NUMBER PRIMARY KEY,
    CUST_NAME VARCHAR(200)
);

SELECT * FROM CUSTOMER_SWIGGY;

CREATE TABLE ORDER_SWIGGY (
    ORDER_ID NUMBER PRIMARY KEY,
    CUST_ID NUMBER,

    CONSTRAINT FK_CUSTOMER FOREIGN KEY (CUST_ID) REFERENCES CUSTOMER_SWIGGY(CUST_ID)
);

SELECT * FROM ORDER_SWIGGY;
```

 **Explanation**:

* `ORDER_SWIGGY` table references `CUSTOMER_SWIGGY`.
* By default, the foreign key is **NOT DEFERRABLE**, so the check is immediate.
* If declared **DEFERRABLE INITIALLY DEFERRED**, we could insert data temporarily violating the constraint and fix it before committing.

---

# Summary of Constraints

| Constraint      | Description                                                          |
| --------------- | -------------------------------------------------------------------- |
| **NOT NULL**    | Prevents NULL values in a column.                                    |
| **CHECK**       | Ensures values satisfy a specific condition.                         |
| **DEFAULT**     | Assigns a default value when none is provided.                       |
| **PRIMARY KEY** | Uniquely identifies a row (combination of NOT NULL + UNIQUE).        |
| **UNIQUE**      | Ensures all values in a column are different (allows one NULL).      |
| **FOREIGN KEY** | Ensures referential integrity between tables.                        |
| **DEFERRABLE**  | Postpones constraint checking until COMMIT (if defined as deferred). |

---


# SQL Practice – Department, Employee, Joins, Synonym, Sequence, and Views

This project demonstrates the use of **Oracle SQL features** like:

* Creating and dropping tables
* Using **Primary keys** and **Foreign keys**
* Working with **Synonyms, Sequences, and Views**
* Performing **Joins** (Inner, Self, Outer)
* Exploring **Set operators** with sample `employee_2024` and `employee_2025` tables

---

##  Table Creation and Setup

### Department Table

```sql
DROP TABLE DEPARTMENT;
CREATE TABLE department (
    dept_id NUMBER PRIMARY KEY,
    dept_name VARCHAR2(50)
);
select * from department;
```

### Employee Table

```sql
DROP TABLE employee;
CREATE TABLE employee (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    salary NUMBER,
    dept_id NUMBER,
    manager_id NUMBER,
    CONSTRAINT fk_dept FOREIGN KEY (dept_id) REFERENCES department(dept_id)
);
SELECT * FROM EMPLOYEE;
```

### Employee\_2024 & Employee\_2025 Tables

For set operator demonstrations:

```sql
CREATE TABLE employee_2024 (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50)
);

CREATE TABLE employee_2025 (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50)
);
```

---

##  Inserting Sample Data

### Department Data

```sql
INSERT INTO department VALUES (10, 'HR');
INSERT INTO department VALUES (20, 'IT');
INSERT INTO department VALUES (30, 'Finance');
INSERT INTO department VALUES (40, 'Marketing');
```

**Output:**

| DEPT\_ID | DEPT\_NAME |
| -------- | ---------- |
| 10       | HR         |
| 20       | IT         |
| 30       | Finance    |
| 40       | Marketing  |

---

### Employee Data

```sql
INSERT INTO employee VALUES (101, 'Ravi', 50000, 10, NULL);   -- Manager HR
INSERT INTO employee VALUES (102, 'Kiran', 45000, 10, 101);
INSERT INTO employee VALUES (103, 'Anjali', 60000, 20, NULL); -- Manager IT
INSERT INTO employee VALUES (104, 'Pavan', 40000, 20, 103);
INSERT INTO employee VALUES (105, 'Sita', 70000, 30, NULL);   -- Manager Finance
INSERT INTO employee VALUES (106, 'Krishna', 38000, 30, 105);
INSERT INTO employee VALUES (107, 'Deepak', 30000, NULL, NULL); -- No dept (to test outer join)
```

**Output:**

| EMP\_ID | EMP\_NAME | SALARY | DEPT\_ID | MANAGER\_ID |
| ------- | --------- | ------ | -------- | ----------- |
| 101     | Ravi      | 50000  | 10       | NULL        |
| 102     | Kiran     | 45000  | 10       | 101         |
| 103     | Anjali    | 60000  | 20       | NULL        |
| 104     | Pavan     | 40000  | 20       | 103         |
| 105     | Sita      | 70000  | 30       | NULL        |
| 106     | Krishna   | 38000  | 30       | 105         |
| 107     | Deepak    | 30000  | NULL     | NULL        |

---

### Employee\_2024 Data

```sql
INSERT INTO employee_2024 VALUES (201, 'Ravi');
INSERT INTO employee_2024 VALUES (202, 'Kiran');
INSERT INTO employee_2024 VALUES (203, 'Sita');
```

### Employee\_2025 Data

```sql
INSERT INTO employee_2025 VALUES (301, 'Ravi');
INSERT INTO employee_2025 VALUES (302, 'Anjali');
INSERT INTO employee_2025 VALUES (303, 'Deepak');
```

---

##  Module 3 – Advanced SQL Features

###  Synonym

* A **Synonym** is an alias (another name) for a database object like a table, view, or sequence.
* Helps in **shortening long names** and **hiding schema details**.

```sql
CREATE SYNONYM emp FOR employee;

SELECT * FROM EMPLOYEE;
SELECT * FROM EMP;
```

Both queries return the same results.

---

###  Sequence

* A **Sequence** generates unique numbers (commonly used for primary keys).
* Prevents duplicate key errors.

```sql
CREATE SEQUENCE EMP_SEQ START WITH 1000 INCREMENT BY 1;

INSERT INTO employee_2024 VALUES (EMP_SEQ.NEXTVAL,'MOHAN');
INSERT INTO employee_2024 VALUES (EMP_SEQ.NEXTVAL,'Arya');
INSERT INTO employee_2024 VALUES (EMP_SEQ.NEXTVAL,'Arun');
INSERT INTO employee_2024 VALUES (EMP_SEQ.NEXTVAL,'Geetha');
```

**Output Example (auto IDs generated):**

| EMP\_ID | EMP\_NAME |
| ------- | --------- |
| 201     | Ravi      |
| 202     | Kiran     |
| 203     | Sita      |
| 1000    | MOHAN     |
| 1001    | Arya      |
| 1002    | Arun      |
| 1003    | Geetha    |

---

###  Views

* A **View** is a **virtual table** based on the result of a query.
* Provides **data security** by restricting access.

```sql
CREATE VIEW EMP_VIEW AS 
SELECT emp_id , emp_name, dept_id
FROM employee
WHERE salary > 40000;

SELECT * FROM EMP_VIEW;
```

**Output:**

| EMP\_ID | EMP\_NAME | DEPT\_ID |
| ------- | --------- | -------- |
| 101     | Ravi      | 10       |
| 102     | Kiran     | 10       |
| 103     | Anjali    | 20       |
| 105     | Sita      | 30       |

---

##  Joins

###  Inner Join (Simple Join)

```sql
SELECT e.emp_id , e.emp_name, d.dept_name 
FROM employee e 
INNER JOIN department d 
ON e.dept_id = d.dept_id;
```

**Output:**

| EMP\_ID | EMP\_NAME | DEPT\_NAME |
| ------- | --------- | ---------- |
| 101     | Ravi      | HR         |
| 102     | Kiran     | HR         |
| 103     | Anjali    | IT         |
| 104     | Pavan     | IT         |
| 105     | Sita      | Finance    |
| 106     | Krishna   | Finance    |

---

### Self Join

```sql
SELECT E1.EMP_NAME AS EMPLOYEE, E2.EMP_NAME AS MANAGER  
FROM EMPLOYEE E1 
JOIN EMPLOYEE E2 
ON E1.MANAGER_ID = E2.EMP_ID;
```

**Output:**

| EMPLOYEE | MANAGER |
| -------- | ------- |
| Kiran    | Ravi    |
| Pavan    | Anjali  |
| Krishna  | Sita    |

---

###  Left Outer Join

```sql
SELECT E.EMP_NAME ,D.DEPT_NAME 
FROM EMPLOYEE E 
LEFT OUTER JOIN DEPARTMENT D 
ON E.DEPT_ID = D.DEPT_ID;
```

**Output:**

| EMP\_NAME | DEPT\_NAME |
| --------- | ---------- |
| Ravi      | HR         |
| Kiran     | HR         |
| Anjali    | IT         |
| Pavan     | IT         |
| Sita      | Finance    |
| Krishna   | Finance    |
| Deepak    | NULL       |

---

### Right Outer Join

```sql
SELECT E.EMP_NAME ,D.DEPT_NAME 
FROM EMPLOYEE E 
RIGHT OUTER JOIN DEPARTMENT D 
ON E.DEPT_ID = D.DEPT_ID;
```

**Output:**

| EMP\_NAME | DEPT\_NAME |
| --------- | ---------- |
| Ravi      | HR         |
| Kiran     | HR         |
| Anjali    | IT         |
| Pavan     | IT         |
| Sita      | Finance    |
| Krishna   | Finance    |
| NULL      | Marketing  |

---

###  Full Outer Join

```sql
SELECT E.EMP_NAME , D.DEPT_NAME 
FROM EMPLOYEE E 
FULL OUTER JOIN DEPARTMENT D 
ON E.DEPT_ID = D.DEPT_ID;
```

**Output:**

| EMP\_NAME | DEPT\_NAME |
| --------- | ---------- |
| Ravi      | HR         |
| Kiran     | HR         |
| Anjali    | IT         |
| Pavan     | IT         |
| Sita      | Finance    |
| Krishna   | Finance    |
| Deepak    | NULL       |
| NULL      | Marketing  |

---

##  Key Takeaways

* **Synonym** → Alias for database objects.
* **Sequence** → Auto-generates unique numbers.
* **View** → Virtual table for simplifying queries and restricting access.
* **Joins** → Combine data across tables:

  * **Inner Join** → Matching rows only
  * **Self Join** → Hierarchical relationships
  * **Left/Right Outer Join** → Include non-matching rows from one side
  * **Full Outer Join** → Includes all rows
 
  ---

# **SQL Subqueries – Complete Notes**

## **What is a Subquery?**

* A **subquery** (also called a **nested query** or **inner query**) is a query **inside another query**.
* The **subquery executes first**, and the result is passed to the **outer query**.
* Subqueries are always enclosed in **parentheses `( )`**.
* Used for **filtering, comparisons, calculations, and temporary results**.

---

## **General Syntax**

```sql
SELECT column_list
FROM table_name
WHERE column_name operator (SELECT column_name FROM table_name WHERE condition);
```

---

## **Types of Subqueries**

1. **Single Row Subquery**
2. **Multi Row Subquery**
3. **Multi Column Subquery**
4. **Correlated Subquery**
5. **Nested Subquery**

---

## **1. Single Row Subquery**

* Returns **only one row**.
* Used with operators: `=, >, <, >=, <=, <>`.

### Example

```sql
-- Find employees whose salary is greater than Ravi's salary
SELECT emp_name, salary
FROM employee
WHERE salary > (SELECT salary FROM employee WHERE emp_name = 'Ravi');
```

### Execution:

* Inner query → Gets Ravi’s salary (e.g., 50000).
* Outer query → Finds all employees with salary > 50000.

### Sample Output:

| emp\_name | salary |
| --------- | ------ |
| Anjali    | 60000  |
| Sita      | 70000  |

---

## **2. Multi Row Subquery**

* Returns **multiple rows**.
* Uses operators: `IN`, `ANY`, `ALL`.

### Example

```sql
-- Find employees who work in the same dept as Kiran or Anjali
SELECT emp_name, dept_id
FROM employee
WHERE dept_id IN (SELECT dept_id FROM employee WHERE emp_name IN ('Kiran','Anjali'));
```

### Execution:

* Inner query → gets dept\_id of Kiran (10) and Anjali (20).
* Outer query → selects all employees in dept 10 or 20.

### Sample Output:

| emp\_name | dept\_id |
| --------- | -------- |
| Ravi      | 10       |
| Kiran     | 10       |
| Anjali    | 20       |
| Pavan     | 20       |

---

## **3. Multi Column Subquery**

* Returns **multiple columns**.
* Used for comparing **two or more values at once**.

 Note: Must use tuple comparison `(col1, col2)` in Oracle.

### Example

```sql
-- Find employees with the same dept and salary as Pavan
SELECT emp_name, dept_id, salary
FROM employee
WHERE (dept_id, salary) IN (SELECT dept_id, salary FROM employee WHERE emp_name = 'Pavan');
```

### Execution:

* Inner query → Gets (20, 40000) for Pavan.
* Outer query → Finds employees with dept\_id=20 and salary=40000.

### Sample Output:

| emp\_name | dept\_id | salary |
| --------- | -------- | ------ |
| Pavan     | 20       | 40000  |

---

## **4. Correlated Subquery**

* Inner query depends on the **outer query row**.
* Executed **once for each row** of outer query.

### Example

```sql
-- Find employees whose salary is greater than avg salary of their own dept
SELECT emp_name, dept_id, salary
FROM employee e
WHERE salary > (SELECT AVG(salary) FROM employee WHERE dept_id = e.dept_id);
```

### Execution:

* For each employee, inner query calculates average salary of that employee’s department.
* Then compares the employee’s salary with dept average.

### Sample Output:

| emp\_name | dept\_id | salary |
| --------- | -------- | ------ |
| Ravi      | 10       | 50000  |
| Anjali    | 20       | 60000  |
| Sita      | 30       | 70000  |

---

## **5. Nested Subquery**

* A subquery inside **another subquery**.

### Example

```sql
-- Find employees who earn more than the min salary in IT dept
SELECT emp_name, dept_id, salary
FROM employee
WHERE salary > (SELECT MIN(salary)
                FROM employee
                WHERE dept_id = (SELECT dept_id FROM department WHERE dept_name = 'IT'));
```

### Execution:

1. Innermost → Gets dept\_id of IT (20).
2. Middle → Finds MIN(salary) of dept 20 (e.g., 40000).
3. Outer → Finds employees with salary > 40000.

### Sample Output:

| emp\_name | dept\_id | salary |
| --------- | -------- | ------ |
| Anjali    | 20       | 60000  |
| Ravi      | 10       | 50000  |
| Sita      | 30       | 70000  |

---

## **Subquery in SELECT Clause**

```sql
SELECT emp_name,
       salary,
       (SELECT dept_name FROM department d WHERE d.dept_id = e.dept_id) AS dept_name
FROM employee e;
```

 Adds department name directly in the result.

---

## **Subquery in FROM Clause (Inline View)**

```sql
SELECT dept_id, AVG(salary) AS avg_salary
FROM (SELECT * FROM employee WHERE salary > 30000)
GROUP BY dept_id;
```

 Treats subquery as a **temporary table**.

---

## **Key Points**

* Subquery executes first, outer query uses its result.
* Single-row subqueries → use comparison operators.
* Multi-row subqueries → use `IN`, `ANY`, `ALL`.
* Correlated subqueries → run row-by-row.
* Nested subqueries → multi-level filtering.

---


# **SQL Set Operators**

## **1. Introduction**

* **Set operators** are used to **combine results of two or more SELECT queries**.
* Both queries must have:

  * Same **number of columns**
  * Same **data types**
  * Same **order of columns**

---

## **2. Types of Set Operators**

1. **UNION** – combines results, removes duplicates
2. **UNION ALL** – combines results, keeps duplicates
3. **INTERSECT** – returns only common rows
4. **MINUS** – returns rows from first query that are not in second

---

## **3. Syntax**

```sql
SELECT column_list FROM table1
<SET_OPERATOR>
SELECT column_list FROM table2;
```

---

# **Step 1: Create Dedicated Tables**

```sql
-- Table 1: Employees in 2024
CREATE TABLE employee_2024 (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    dept VARCHAR2(30)
);

-- Table 2: Employees in 2025
CREATE TABLE employee_2025 (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    dept VARCHAR2(30)
);
```

---

# **Step 2: Insert Large Sample Data**

```sql
-- Employee 2024 Data
INSERT INTO employee_2024 VALUES (201, 'Ravi', 'HR');
INSERT INTO employee_2024 VALUES (202, 'Kiran', 'IT');
INSERT INTO employee_2024 VALUES (203, 'Sita', 'Finance');
INSERT INTO employee_2024 VALUES (204, 'Anjali', 'IT');
INSERT INTO employee_2024 VALUES (205, 'Deepak', 'Marketing');
INSERT INTO employee_2024 VALUES (206, 'Krishna', 'Finance');
INSERT INTO employee_2024 VALUES (207, 'Pavan', 'IT');
INSERT INTO employee_2024 VALUES (208, 'Mohan', 'HR');

-- Employee 2025 Data
INSERT INTO employee_2025 VALUES (301, 'Ravi', 'HR');
INSERT INTO employee_2025 VALUES (302, 'Anjali', 'IT');
INSERT INTO employee_2025 VALUES (303, 'Deepak', 'Marketing');
INSERT INTO employee_2025 VALUES (304, 'Surya', 'Finance');
INSERT INTO employee_2025 VALUES (305, 'Kiran', 'IT');
INSERT INTO employee_2025 VALUES (306, 'Sita', 'Finance');
INSERT INTO employee_2025 VALUES (307, 'Rajesh', 'HR');
INSERT INTO employee_2025 VALUES (308, 'Meena', 'IT');
```

---

# **Step 3: Demonstrating Set Operators**

---

## **1. UNION**

* Combines rows from both queries.
* Removes duplicates.

```sql
SELECT emp_name, dept FROM employee_2024
UNION
SELECT emp_name, dept FROM employee_2025;
```

### Sample Output

| emp\_name | dept      |
| --------- | --------- |
| Ravi      | HR        |
| Kiran     | IT        |
| Sita      | Finance   |
| Anjali    | IT        |
| Deepak    | Marketing |
| Krishna   | Finance   |
| Pavan     | IT        |
| Mohan     | HR        |
| Surya     | Finance   |
| Rajesh    | HR        |
| Meena     | IT        |

 Duplicates removed (e.g., Ravi, Anjali, Sita).

---

## **2. UNION ALL**

* Combines rows from both queries.
* Keeps duplicates.

```sql
SELECT emp_name, dept FROM employee_2024
UNION ALL
SELECT emp_name, dept FROM employee_2025;
```

### Sample Output

| emp\_name | dept      |                  |
| --------- | --------- | ---------------- |
| Ravi      | HR        |                  |
| Kiran     | IT        |                  |
| Sita      | Finance   |                  |
| Anjali    | IT        |                  |
| Deepak    | Marketing |                  |
| Krishna   | Finance   |                  |
| Pavan     | IT        |                  |
| Mohan     | HR        |                  |
| Ravi      | HR        |  Duplicate kept  |
| Anjali    | IT        |                  |
| Deepak    | Marketing |                  |
| Surya     | Finance   |                  |
| Kiran     | IT        |                  |
| Sita      | Finance   |                  |
| Rajesh    | HR        |                  |
| Meena     | IT        |                  |

---

## **3. INTERSECT**

* Returns **only rows present in both queries**.

```sql
SELECT emp_name, dept FROM employee_2024
INTERSECT
SELECT emp_name, dept FROM employee_2025;
```

### Sample Output

| emp\_name | dept      |
| --------- | --------- |
| Ravi      | HR        |
| Kiran     | IT        |
| Sita      | Finance   |
| Anjali    | IT        |
| Deepak    | Marketing |

 Only common employees in both tables.

---

## **4. MINUS**

* Returns rows in first query **not present in second query**.

```sql
SELECT emp_name, dept FROM employee_2024
MINUS
SELECT emp_name, dept FROM employee_2025;
```

### Sample Output

| emp\_name | dept    |
| --------- | ------- |
| Krishna   | Finance |
| Pavan     | IT      |
| Mohan     | HR      |

These employees are only in **2024**, not in **2025**.

---

# **4. Summary of Operators**

| Operator      | Removes Duplicates? | Shows Common? | Shows Differences?    |
| ------------- | ------------------- | ------------- | --------------------- |
| **UNION**     |  Yes                | Combines both |  No                   |
| **UNION ALL** |  No                 | Combines both |  No                   |
| **INTERSECT** |  Yes                |  Only common  |  No                   |
| **MINUS**     |  Yes                |  No           |  Yes (first – second) |

---

# **5. When to Use**

* **UNION** → merging unique rows
* **UNION ALL** → merging all rows including duplicates
* **INTERSECT** → finding common records between datasets
* **MINUS** → finding differences (what exists in one table but not the other)

---
Here’s the full content you provided converted into **Markdown format** for your GitHub `README.md` file.
I’ve preserved everything exactly as is, without deleting or shortening, and also formatted it properly with **headings, code blocks, bullet points, and explanations**.

You can directly copy-paste this into your `README.md` file.

---

# PL/SQL (Procedural Language/SQL) Notes

PL/SQL (Procedural Language/SQL) is Oracle’s extension of SQL that adds procedural features like loops, conditions, and error handling. It allows developers to write powerful programs that combine SQL queries with logic to control how data is processed. With PL/SQL, complex operations, calculations, and error handling can be performed directly within the Oracle database, making data manipulation more efficient and flexible.

---

## What PL/SQL Allows Developers to Do

* Execute SQL queries and DML commands inside procedural blocks.
* Define variables and perform complex calculations.
* Create reusable program units, such as procedures, functions, and triggers.
* Handle exceptions, ensuring the program runs smoothly even when errors occur.

---

## Key Features of PL/SQL

PL/SQL brings the benefits of procedural programming to the relational database world. Some of the most important features of PL/SQL include:

* **Block Structure**: PL/SQL can execute a number of queries in one block using a single command.
* **Procedural Constructs**: One can create a PL/SQL unit such as procedures, functions, packages, triggers, and types, which are stored in the database for reuse by applications.
* **Error Handling**: PL/SQL provides a feature to handle exceptions that occur in a PL/SQL block, known as the exception handling block.
* **Reusable Code**: Create stored procedures, functions, triggers, and packages, which can be executed repeatedly.
* **Performance**: Reduces network traffic by executing multiple SQL statements within a single block.

---

## Structure of a PL/SQL Block

PL/SQL extends SQL by adding constructs found in procedural languages, resulting in a structural language that is more powerful than SQL. The basic unit in PL/SQL is a **block**. All PL/SQL programs are made up of blocks, which can be nested within each other.

Typically, each block performs a logical action in the program. A block has the following structure:

<img width="455" height="300" alt="image" src="https://github.com/user-attachments/assets/599c3c46-8978-4d1a-a22c-552a007d9a46" />


```sql
DECLARE
    declaration statements;

BEGIN
    executable statements;

EXCEPTION
    exception handling statements;

END;
/
```

### Sections of a PL/SQL Block

* **Declare Section**

  * Starts with `DECLARE` keyword.
  * Variables, constants, records, and cursors can be declared here to store data temporarily.
  * Basically consists of the definition of PL/SQL identifiers.
  * *Optional section*.

* **Execution Section**

  * Starts with `BEGIN` and ends with `END`.
  * This is a **mandatory section**.
  * Contains program logic to perform tasks like loops and conditional statements.
  * Supports all **DML commands, DDL commands, and SQL\*PLUS built-in functions**.

* **Exception Section**

  * Starts with `EXCEPTION` keyword.
  * *Optional section*.
  * Contains statements that are executed when a runtime error occurs.
  * Any exceptions can be handled here.

---

## PL/SQL Identifiers

In PL/SQL, identifiers are names used to represent various program elements like variables, constants, procedures, cursors, triggers, etc. These identifiers allow you to store, manipulate, and access data throughout your PL/SQL code.

---

### 1. Variables in PL/SQL

Like several other programming languages, variables in PL/SQL must be declared prior to use. A variable is like a container that holds data during program execution. Each variable must have:

* A valid name
* A specific data type

#### Syntax for Declaration of Variables:

```sql
variable_name datatype [NOT NULL := value];
```

* `variable_name`: The name of the variable.
* `datatype`: The data type of the variable (e.g., INTEGER, VARCHAR2).
* `NOT NULL`: Optional constraint, meaning the variable cannot be left empty.
* `:= value`: Optional assignment, assigns an initial value to the variable.

---

#### Example: Declaring Variables

```sql
SQL> SET SERVEROUTPUT ON;

SQL> DECLARE
    var1 INTEGER;
    var2 REAL;
    var3 VARCHAR2(20);

BEGIN
    NULL;
END;
/
```

**Output:**

```
PL/SQL procedure successfully completed.
```

**Explanation:**

* `SET SERVEROUTPUT ON`: Displays the buffer used by `DBMS_OUTPUT`.
* `var1 INTEGER`: Declares a variable named `var1` of type integer.
* Many other data types are supported such as `FLOAT`, `INT`, `REAL`, `SMALLINT`, `LONG`, `NUMBER(prec, scale)`, `VARCHAR`, `VARCHAR2`, etc.
* Slash `/` after `END;`: Executes the block in SQL\*Plus.
* Assignment operator `:=`: Used to assign a value to a variable.

---

### 2. Displaying Output in PL/SQL

The outputs are displayed using **`DBMS_OUTPUT`**, which is a built-in package that enables the user to display output, debugging information, and send messages from PL/SQL blocks, subprograms, packages, and triggers.

#### Example: Displaying Output

```sql
SQL> SET SERVEROUTPUT ON;
SQL> DECLARE
     var VARCHAR2(40) := 'I love INDIA';

BEGIN
     DBMS_OUTPUT.PUT_LINE(var);

END;
/
```

**Output:**

```
I love INDIA
PL/SQL procedure successfully completed.
```

**Explanation:**

* `DBMS_OUTPUT.PUT_LINE`: Directs the PL/SQL output to the screen.

---

### 3. Comments in PL/SQL

Like in many other programming languages, comments in PL/SQL have no effect on code execution. They can be used to add explanations or notes.

#### Types of Comments:

* **Single-Line Comment**: Use `--`
* **Multi-Line Comment**: Use `/* */`

#### Example: Adding Comments

```sql
-- This is a single-line comment

/*
  This is a multi-line comment
  that spans over multiple lines.
*/
```

---

# PL/SQL Architecture

---
<img width="693" height="397" alt="image" src="https://github.com/user-attachments/assets/8ae92bb3-8b31-4ef2-88f0-6f5edff9a94e" />


## What do you mean by PL/SQL?

In Oracle, **PL/SQL (Procedural Language/SQL)** is the procedural language extension to the non-procedural SQL. It combines the data manipulation power of SQL and the procedural power of standard programming languages.

* PL/SQL was developed by **Oracle Corporation** within the early '90s to reinforce the capabilities of SQL.
* It integrates well with **SQL\*PLUS** and other application development products of Oracle.
* PL/SQL is the **superset of SQL**. It provides SQL data manipulation commands and SQL data types.
* In PL/SQL, a block without any name is called **Anonymous Block**.
* A PL/SQL block consists of various **functions, libraries, procedures, triggers, and packages**.

---

### Rules & Best Practices to Remember

* In PL/SQL, the **semicolon (;)** is placed at the end of an SQL statement or PL/SQL control statement.
* Section keywords **DECLARE**, **BEGIN**, and **EXCEPTION** are **not** followed by semicolons.
* The **END** keyword and all other PL/SQL statements require a **semicolon (;)** to terminate the statements.
* Before you start creating code, **define the goals and capabilities** of your PL/SQL software.
* Select names for constants, variables, and other identifiers that are **both meaningful and descriptive**.
* To keep track of modifications in your PL/SQL code, use **version control tools** (like Git).
* Keep the use of **global/universal variables** to a minimum.
* Observe the **least privilege principle**.
* Use the **COMMIT** and **ROLLBACK** instructions to provide proper transaction management.

---

## Features of PL/SQL

The various features of PL/SQL are given below:

* Runs on various operating systems such as **Windows, Linux, etc.**
* Provides an **error-checking facility** and displays user-friendly messages when an error occurs.
* Offers **logging and debugging capabilities**, including the capacity to use exception messages.
* SQL can be executed **dynamically**.
* **Triggers** are specialized forms of stored processes that are automatically invoked when certain data events occur (e.g., `INSERT`, `UPDATE`, or `DELETE`).
* **Cursors** are used to handle multi-row queries.
* Supports declaration of **variables and constants** to store data values.

---

## What do you mean by PL/SQL Architecture?

The **PL/SQL runtime system** is a technology (not an independent product).
It works like an **engine** that executes PL/SQL blocks, subprograms (like functions and procedures).

* This engine can be installed in:

  * An **Oracle Server**
  * Application development tools such as **Oracle Form Builder** or **Oracle Reports Builder**

---

### PL/SQL Architecture Workflow

* PL/SQL can reside in **two environments**:

  1. **The Oracle Server**
  2. **The Oracle Tools**

* These two environments are **independent** of each other.

* In either environment, the PL/SQL engine accepts any valid **PL/SQL block** as input.

* The PL/SQL engine executes the **procedural part** of the statements and sends the **SQL statements** to the Oracle Server for execution.

* Only a **single transfer** is required to send the block from the application to the Oracle Server, improving performance (especially in a Client-Server network).

* PL/SQL code can also be **stored in the Oracle server** as subprograms, which can be referenced by any number of applications connected to the database.

---

## Advantages of PL/SQL

* Provides **better performance**.
* Ensures **high productivity**.
* Supports **Object-Oriented Programming concepts**.
* Offers **scalability and manageability**.
* Supports various **web application development tools**.

---

## Disadvantages of PL/SQL

* Requires **high memory**.
* Lacks **functionality debugging** in stored procedures.

---

#  PL/SQL Scalar Data Types 

In **PL/SQL**, scalar data types are the fundamental building blocks for handling single values. Unlike composite types (arrays, records, etc.), scalar types hold **one value at a time**.

Scalar data types include:

*  **Numeric Types**
*  **Character Types**
*  **Boolean Types**
*  **Datetime & Interval Types**
*  **Large Object (LOB) Types**

---

##  Numeric Data Types

Used to store numbers (integers, decimals, floating point).

### 1. **NUMBER**

* Can be used as **fixed point** or **floating point**.
* Syntax:

  ```sql
  NUMBER(p, s)
  ```

  * `p` → Precision (total digits).
  * `s` → Scale (digits after decimal).

Example:

```sql
v_num NUMBER(5,2) := 123.45; -- allows 5 digits, 2 after decimal
```

---

### 2. **BINARY\_INTEGER / PLS\_INTEGER**

* Store signed integers.
* `PLS_INTEGER` is faster (machine-dependent, efficient for loops).

 Example:

```sql
v_int BINARY_INTEGER := 100;
v_plsint PLS_INTEGER := -50;
```

---

### 3. **FLOAT**

* Stores floating-point values with precision up to **10 digits**.

 Example:

```sql
v_float FLOAT(10) := 12345.6789;
```

---

###  Subtypes of NUMBER

PL/SQL provides **constraint subtypes** of `BINARY_INTEGER` for safer coding:

| Subtype       | Description                             | Example                   |
| ------------- | --------------------------------------- | ------------------------- |
| **NATURAL**   | Non-negative integers (0,1,2,3,…)       | `v_nat NATURAL := 0;`     |
| **NATURALN**  | Like NATURAL, but **cannot be NULL**    | `v_natn NATURALN := 10;`  |
| **POSITIVE**  | Only positive (>0) integers             | `v_pos POSITIVE := 20;`   |
| **POSITIVEN** | Positive (>0) integers and **not NULL** | `v_posn POSITIVEN := 30;` |

 Useful when you want to restrict values to safe ranges.

---

##  Character Data Types

Used to store text strings.

### 1. **CHAR**

* Fixed-length character string.
* Pads with spaces if shorter.
   Example:

```sql
v_char CHAR(10) := 'HELLO'; -- stored as 'HELLO     '
```

---

### 2. **VARCHAR2**

* Variable-length string.
* Preferred over `CHAR`.
   Example:

```sql
v_varchar VARCHAR2(20) := 'Oracle PL/SQL';
```

---

### 3. **LONG**

* Stores variable-length strings **up to 2GB**.
* Rarely used (deprecated, replaced by `CLOB`).
   Example:

```sql
v_long LONG := 'This is a long string...';
```

---

###  Subtypes of Character

| Subtype          | Description                                |
| ---------------- | ------------------------------------------ |
| **STRING**       | Subtype of `VARCHAR2` for variable strings |
| **LONG VARCHAR** | Used for large variable strings            |

 Example:

```sql
v_string STRING(50) := 'Variable length string';
v_longvar VARCHAR2(2000) := 'Large string storage demo';
```

---

##  Boolean Data Type

* Stores logical values: `TRUE`, `FALSE`, or `NULL`.
* Cannot be selected from a database column directly.

 Example:

```sql
v_bool BOOLEAN := TRUE;

IF v_bool THEN
   DBMS_OUTPUT.PUT_LINE('BOOLEAN: TRUE');
END IF;
```

---

##  Date & Time Data Types

Used to handle dates, times, and intervals.

### 1. **DATE**

* Stores date + time (year, month, day, hour, min, sec).
   Example:

```sql
v_date DATE := SYSDATE;
```

---

### 2. **TIMESTAMP**

* More precise than `DATE` (includes fractional seconds).
   Example:

```sql
v_ts TIMESTAMP := SYSTIMESTAMP;
```

---

### 3. **TIMESTAMP WITH TIME ZONE**

* Stores date + time + time zone info.
   Example:

```sql
v_tstz TIMESTAMP WITH TIME ZONE := SYSTIMESTAMP;
```

---

### 4. **TIMESTAMP WITH LOCAL TIME ZONE**

* Normalizes time zone according to **DB session’s time zone**.

---

### 5. **INTERVAL YEAR TO MONTH**

* Represents differences in **years and months**.
   Example:

```sql
v_intv_ym INTERVAL YEAR TO MONTH := INTERVAL '2' YEAR;
```

---

### 6. **INTERVAL DAY TO SECOND**

* Represents differences in **days, hours, minutes, seconds**.
   Example:

```sql
v_intv_ds INTERVAL DAY TO SECOND := INTERVAL '5 12:30:45' DAY TO SECOND;
```

---

## Large Object (LOB) Data Types

Used for handling **large unstructured data** like images, videos, documents.

| LOB Type  | Description                                    |
| --------- | ---------------------------------------------- |
| **BLOB**  | Binary Large Object (images, multimedia, etc.) |
| **CLOB**  | Character Large Object (large text up to 4GB)  |
| **NCLOB** | National character large object (Unicode text) |
| **BFILE** | Pointer to a binary file stored outside DB     |

Note: LOB values cannot be directly printed using `DBMS_OUTPUT`.

---

## Full Example Program (Demo)

```sql
SET SERVEROUTPUT ON;

DECLARE
    -- Numeric Types
    v_num1      NUMBER(5,2) := 123.45;
    v_int       BINARY_INTEGER := 100;
    v_plsint    PLS_INTEGER := -50;
    v_float     FLOAT(10) := 12345.6789;

    v_nat       NATURAL := 0;
    v_natn      NATURALN := 10;
    v_pos       POSITIVE := 20;
    v_posn      POSITIVEN := 30;

    -- Character Types
    v_char      CHAR(10) := 'HELLO';
    v_varchar   VARCHAR2(20) := 'Oracle PL/SQL';
    v_long      LONG := 'This is a long string...';
    v_string    STRING(50) := 'Variable length string';
    v_longvar   VARCHAR2(2000) := 'Large string storage demo';

    -- Boolean
    v_bool      BOOLEAN := TRUE;

    -- Date & Time
    v_date      DATE := SYSDATE;
    v_ts        TIMESTAMP := SYSTIMESTAMP;
    v_tstz      TIMESTAMP WITH TIME ZONE := SYSTIMESTAMP;
    v_tslz      TIMESTAMP WITH LOCAL TIME ZONE := SYSTIMESTAMP;
    v_intv_ym   INTERVAL YEAR TO MONTH := INTERVAL '2' YEAR;
    v_intv_ds   INTERVAL DAY TO SECOND := INTERVAL '5 12:30:45' DAY TO SECOND;

    -- LOBs
    v_blob      BLOB;
    v_clob      CLOB;
    v_nclob     NCLOB;
    v_bfile     BFILE;
BEGIN
    -- Numeric
    DBMS_OUTPUT.PUT_LINE('NUMBER: ' || v_num1);
    DBMS_OUTPUT.PUT_LINE('BINARY_INTEGER: ' || v_int);
    DBMS_OUTPUT.PUT_LINE('PLS_INTEGER: ' || v_plsint);
    DBMS_OUTPUT.PUT_LINE('FLOAT: ' || v_float);

    DBMS_OUTPUT.PUT_LINE('NATURAL: ' || v_nat);
    DBMS_OUTPUT.PUT_LINE('NATURALN: ' || v_natn);
    DBMS_OUTPUT.PUT_LINE('POSITIVE: ' || v_pos);
    DBMS_OUTPUT.PUT_LINE('POSITIVEN: ' || v_posn);

    -- Character
    DBMS_OUTPUT.PUT_LINE('CHAR: ' || v_char);
    DBMS_OUTPUT.PUT_LINE('VARCHAR2: ' || v_varchar);
    DBMS_OUTPUT.PUT_LINE('LONG: ' || v_long);
    DBMS_OUTPUT.PUT_LINE('STRING: ' || v_string);
    DBMS_OUTPUT.PUT_LINE('LONG VARCHAR: ' || v_longvar);

    -- Boolean
    IF v_bool THEN
        DBMS_OUTPUT.PUT_LINE('BOOLEAN: TRUE');
    ELSE
        DBMS_OUTPUT.PUT_LINE('BOOLEAN: FALSE or NULL');
    END IF;

    -- Date & Time
    DBMS_OUTPUT.PUT_LINE('DATE: ' || TO_CHAR(v_date, 'DD-MON-YYYY HH24:MI:SS'));
    DBMS_OUTPUT.PUT_LINE('TIMESTAMP: ' || v_ts);
    DBMS_OUTPUT.PUT_LINE('TIMESTAMP WITH TZ: ' || v_tstz);
    DBMS_OUTPUT.PUT_LINE('TIMESTAMP WITH LOCAL TZ: ' || v_tslz);
    DBMS_OUTPUT.PUT_LINE('INTERVAL YEAR TO MONTH: ' || v_intv_ym);
    DBMS_OUTPUT.PUT_LINE('INTERVAL DAY TO SECOND: ' || v_intv_ds);

    DBMS_OUTPUT.PUT_LINE('LOB Types Declared: BLOB, CLOB, NCLOB, BFILE');
END;
/
```

---
