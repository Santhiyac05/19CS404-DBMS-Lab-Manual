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
--
--<img width="947" height="459" alt="image" src="https://github.com/user-attachments/assets/ec6cc6ba-9c7e-44ea-9e5d-20b67fbc005c" />


```sql
-- CREATE TABLE Products
(
ProductID INTEGER,
ProductName TEXT,
Price REAL,
Stock INTEGER
);
```

**Output:**

!<img width="1212" height="391" alt="image" src="https://github.com/user-attachments/assets/fd800470-ad21-4eb5-8fa6-4b7800d1b9e1" />


**Question 2**
---
-- <img width="702" height="356" alt="image" src="https://github.com/user-attachments/assets/100ea827-22b6-41cd-8b0f-68d6ee556e4e" />


```sql
-- INSERT INTO Employee(EmployeeID, Name, Department, Salary)
SELECT  EmployeeID, Name, Department, Salary FROM Former_employees;
```

**Output:**

!<img width="1212" height="333" alt="image" src="https://github.com/user-attachments/assets/e6a90abc-3a7a-431e-bb54-2201d6b5c683" />


**Question 3**
---
-- <img width="1209" height="440" alt="image" src="https://github.com/user-attachments/assets/c00fef23-b34e-48eb-85c4-cbb7fc2909af" />

```sql
CREATE TABLE Employees
(
EmployeeID primary key,
FirstName VARCHAR(240) NOT NULL,
LastName VARCHAR(240)NOT NULL,
Email VARCHAR(240) UNIQUE,
Salary CHECK(Salary>0),
DepartmentID INTEGER,
foreign key(DepartmentID) references Departments(DepartmentID)
);
```

**Output:**

<img width="1218" height="503" alt="image" src="https://github.com/user-attachments/assets/e670d2f0-44c2-4b29-b757-2bf0c7e29eb5" />


**Question 4**
---
-- <img width="1225" height="498" alt="image" src="https://github.com/user-attachments/assets/61119004-8145-4f2c-958f-d5ae135b8048" />


```sql
CREATE TABLE orders
(
ord_id TEXT NOT NULL CHECK(LENGTH(ord_id)=4),
item_id TEXT NOT NULL,
ord_date DATE,
ord_qty INTEGER,
cost INTEGER,
primary key(item_id,ord_date)
);
```

**Output:**

<img width="1208" height="401" alt="image" src="https://github.com/user-attachments/assets/aeceac52-9758-4cd6-944a-f93c62d0febd" />


**Question 5**
---
-- <img width="939" height="385" alt="image" src="https://github.com/user-attachments/assets/7347265f-c280-4dd6-890f-3904de373de6" />


```sql
INSERT INTO products(Name,Category,Price,Stock)
VALUES('Smartphone','Electronics','800','150'),
('Headphones','Accessories','200','300')
```

**Output:**
<img width="1221" height="420" alt="image" src="https://github.com/user-attachments/assets/2aca18be-4720-485c-a027-d3101a3a16ca" />


**Question 6**
---
--<img width="1183" height="587" alt="image" src="https://github.com/user-attachments/assets/c67ba64d-28b5-4511-bec0-19e379fe01c8" />


```sql
ALTER TABLE 'customer' 
ADD COLUMN discount DECIMAL(5,2);
```

**Output:**
<img width="1212" height="430" alt="image" src="https://github.com/user-attachments/assets/ec631a1c-160c-46ae-9e14-5add0281b579" />

**Question 7**
---
-- <img width="1069" height="488" alt="image" src="https://github.com/user-attachments/assets/da66a5af-347e-4190-98de-773a76a21c52" />


```sql
INSERT INTO Student_details(RollNo,Name,Gender)
VALUES('204','Samuel Black','M')
```

**Output:**

<img width="1199" height="386" alt="image" src="https://github.com/user-attachments/assets/17d747d5-4a25-4b5d-9ab6-dd306102c06b" />


**Question 8**
---
-- <img width="1215" height="442" alt="image" src="https://github.com/user-attachments/assets/b71466a4-2c4d-4e80-bf0a-777c44f9d3fb" />


```sql
<img width="1215" height="442" alt="image" src="https://github.com/user-attachments/assets/bea93282-5ede-4245-b017-d19f54324954" />

```

**Output:**

<img width="1221" height="398" alt="image" src="https://github.com/user-attachments/assets/ef1f05e0-4db6-4ad4-b6f4-eb03af893f55" />


**Question 9**
---
-- <img width="1066" height="601" alt="image" src="https://github.com/user-attachments/assets/454274ac-36a4-4b3c-8995-233e7341bbd4" />


```sql
ALTER TABLE 'Student_details'
ADD COLUMN State TEXT
```

**Output:**

<img width="1220" height="433" alt="image" src="https://github.com/user-attachments/assets/52f8a304-e8b8-4946-82aa-194bb128475f" />


**Question 10**
---
-- <img width="1009" height="462" alt="image" src="https://github.com/user-attachments/assets/c8e5a5e0-739a-4808-acf3-e876e8054301" />


```sql
CREATE TABLE item
(
item_id TEXT primary key,
item_desc TEXT,
rate INTEGER,
icom_id TEXT(4),
foreign key(icom_id) references company(com_id)
ON UPDATE SET NULL
ON DELETE SET NULL
);
```

**Output:**

<img width="1225" height="420" alt="image" src="https://github.com/user-attachments/assets/8baa42c0-9f76-4f89-aa70-3f12d43cf6f1" />

GRADE 
<img width="1353" height="88" alt="image" src="https://github.com/user-attachments/assets/855ccbee-6862-4615-8ed6-4e7944b0c0ca" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
