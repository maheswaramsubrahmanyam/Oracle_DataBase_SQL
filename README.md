# Oracle_DataBase_SQL

Here’s your content converted into **Markdown (`README.md`) format** so you can directly use it for storing notes in your GitHub repo:

````markdown
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

```
Perfect 👍 Let’s extend your notes into a **README.md** file for **DML (Data Manipulation Language)** with clear **theory + syntax + examples** in Markdown.

Here’s the formatted version:

````markdown
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

