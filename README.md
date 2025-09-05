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
