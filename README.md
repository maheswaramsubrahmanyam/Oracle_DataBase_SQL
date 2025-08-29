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

