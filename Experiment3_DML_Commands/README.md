# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="871" height="468" alt="image" src="https://github.com/user-attachments/assets/887417cd-fd84-49a7-af8d-65af42c870d6" />


```sql
UPDATE suppliers
SET supplier_name = UPPER(supplier_name)
WHERE contact_person LIKE '% Singh';
```

**Output:**
<img width="858" height="421" alt="image" src="https://github.com/user-attachments/assets/32133bf3-77ac-422b-9fbe-f1d1efb19a6f" />



**Question 2**
---
<img width="855" height="581" alt="image" src="https://github.com/user-attachments/assets/c8e7bd90-d9db-4881-8726-c79659402874" />


```sql
UPDATE PRODUCTS
SET reorder_lvl='40'
WHERE category='Grocery';
```

**Output:**
<img width="869" height="477" alt="image" src="https://github.com/user-attachments/assets/a0fa172e-b799-4cdf-9dcd-96cdcf447d2c" />


**Question 3**
---
<img width="872" height="267" alt="image" src="https://github.com/user-attachments/assets/4ec48f8f-3636-46c6-b4f9-a61b5be957a4" />


```sql
UPDATE products
SET availability=availability*2
WHERE product_id='1';
```

**Output:**

<img width="866" height="319" alt="image" src="https://github.com/user-attachments/assets/0e231541-b490-4e54-aaec-e5e72d0724e2" />


**Question 4**
---
<img width="859" height="122" alt="image" src="https://github.com/user-attachments/assets/8aa48547-7b9f-41f1-b4ea-3765d69bd22b" />


```sql
UPDATE Customer
SET grade='5'
WHERE city='Chennai';
```

**Output:**

<img width="860" height="478" alt="image" src="https://github.com/user-attachments/assets/6b2c6b48-3da0-4a44-86ce-843233c72318" />


**Question 5**
---
<img width="1222" height="686" alt="image" src="https://github.com/user-attachments/assets/11276e1e-5910-42f4-80e9-ef1cebd39998" />



```sql
DELETE FROM Customer
WHERE WORKING_AREA='New York';
```

**Output:**
<img width="851" height="741" alt="image" src="https://github.com/user-attachments/assets/7d055597-f9f5-4b11-97c0-f4149d1b064e" />


**Question 6**
---
<img width="862" height="589" alt="image" src="https://github.com/user-attachments/assets/dc1a2da9-e6b5-458d-a859-6be8b81aa92e" />


```sql
DELETE FROM Doctors
WHERE last_name IS NULL;
```

**Output:**

<img width="863" height="760" alt="image" src="https://github.com/user-attachments/assets/1060b54f-77f1-4c83-8704-d066c5772e81" />


**Question 7**
---
<img width="844" height="543" alt="image" src="https://github.com/user-attachments/assets/ead196f8-63fd-4ac6-97e7-75e933235976" />


```sql
SELECT *
FROM EmployeeInfo
WHERE Address = 'Delhi(DEL)';
```

**Output:**
<img width="860" height="337" alt="image" src="https://github.com/user-attachments/assets/f9745321-29fc-4eab-ac15-32a479910600" />



**Question 8**
---
<img width="836" height="478" alt="image" src="https://github.com/user-attachments/assets/54f1bec5-86f9-4f94-9000-c0fd17338feb" />


```sql
SELECT CategoryName, Description
FROM categories
ORDER BY CategoryName;
```

**Output:**

<img width="867" height="621" alt="image" src="https://github.com/user-attachments/assets/a0d59fab-41e2-40a9-8bf4-0e8b28a43dfc" />


**Question 9**
---
<img width="876" height="647" alt="image" src="https://github.com/user-attachments/assets/5b0f47d9-4dd9-4cc4-8034-2d7a7d2f0d30" />


```sql
SELECT 
    id,
    value1,
    CASE
        WHEN value1 < 13 THEN 'Child'
        WHEN value1 BETWEEN 13 AND 19 THEN 'Teen'
        ELSE 'Adult'
    END AS age_group
FROM Calculations;
```

**Output:**

<img width="848" height="425" alt="image" src="https://github.com/user-attachments/assets/dd86985b-40df-442b-95d7-638db134ede1" />


**Question 10**
---
<img width="868" height="555" alt="image" src="https://github.com/user-attachments/assets/f51d00a9-7407-4b4c-94d7-d49e546d4803" />



```sql
SELECT customer_id, cust_name, city, grade, salesman_id
FROM customer
WHERE city = 'New York' OR grade <= 100;
```

**Output:**
<img width="860" height="514" alt="image" src="https://github.com/user-attachments/assets/12782ba5-7b6d-4a33-9468-3d35ec36419a" />

GRADES:
<img width="811" height="133" alt="image" src="https://github.com/user-attachments/assets/948b4377-4f77-4257-941a-17fc3cba30ef" />

<img width="819" height="134" alt="image" src="https://github.com/user-attachments/assets/09ea6f56-1308-404a-9091-7b1e0b16d2f7" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
