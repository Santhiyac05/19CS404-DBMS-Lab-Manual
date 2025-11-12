# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="887" height="453" alt="image" src="https://github.com/user-attachments/assets/52b1258f-3450-441e-a304-86f8e7328133" />


```sql
SELECT c.cust_name, s.name
FROM customer c
LEFT JOIN salesman s
  ON c.salesman_id = s.salesman_id
 AND c.city = s.city
WHERE s.name IS NOT NULL;

```

**Output:**

<img width="850" height="549" alt="image" src="https://github.com/user-attachments/assets/0a2d1850-6d74-4495-859d-456320e4019b" />



**Question 2**
---
<img width="880" height="370" alt="image" src="https://github.com/user-attachments/assets/84c678f5-cc7c-463b-8ea4-55d0c6708e37" />


```sql
SELECT DISTINCT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
WHERE c.city = 'New York';

```

**Output:**

<img width="893" height="385" alt="image" src="https://github.com/user-attachments/assets/9ae55a60-8cfe-40d2-8a8c-9bead230465e" />


**Question 3**
---
<img width="1257" height="837" alt="image" src="https://github.com/user-attachments/assets/a11709f9-c3b1-4f76-833b-1a7ee97ac567" />


```sql
select c.cust_name,c.city ,c.grade,s.name as Salesman,s.city 
from customer c
INNER JOIN salesman s ON c.salesman_id=s.salesman_id
where c.grade<300
order by c.customer_id asc;
```

**Output:**


<img width="871" height="755" alt="image" src="https://github.com/user-attachments/assets/ee2fe0fc-f1ae-49d9-95dc-76e45296f26a" />


**Question 4**
---

<img width="894" height="654" alt="image" src="https://github.com/user-attachments/assets/ec127bec-8411-4e45-91d4-7bb491877fbd" />


```sql
SELECT p.first_name, s.*
FROM patients p
INNER JOIN surgeries s ON p.patient_id = s.patient_id
WHERE p.discharge_date  BETWEEN '2024-03-01' and '2024-03-31' 

```

**Output:**


<img width="879" height="408" alt="image" src="https://github.com/user-attachments/assets/29af2f65-6e87-4a7e-9a86-701a1617dc40" />

**Question 5**
---

<img width="885" height="739" alt="image" src="https://github.com/user-attachments/assets/0aae9fa1-267b-4cc9-af35-e159d45e119c" />


```sql
SELECT 
    n.*
FROM 
    nurses n
INNER JOIN 
    departments d ON n.department_id = d.department_id
WHERE 
    d.department_name = 'Pediatrics';

```

**Output:**

<img width="892" height="425" alt="image" src="https://github.com/user-attachments/assets/29a88f07-de5c-42e2-95ee-1dc0b990d7a0" />



**Question 6**
---

<img width="871" height="692" alt="image" src="https://github.com/user-attachments/assets/db459676-87f5-4e13-9de3-3fa854505791" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM customer c
LEFT JOIN orders o 
    ON c.customer_id = o.customer_id
LEFT JOIN salesman s
    ON c.salesman_id = s.salesman_id;

```

**Output:**

<img width="863" height="776" alt="image" src="https://github.com/user-attachments/assets/5e56d4ef-563f-4e3b-800c-b427fbd42966" />




**Question 7**
---

<img width="890" height="836" alt="image" src="https://github.com/user-attachments/assets/efdf33c1-7194-4fff-9179-4969e019df12" />


```sql
select c.cust_name as 'Customer Name',c.city,s.name as Salesman,s.city,s.commission
from customer as c
inner join salesman as s on c.salesman_id=s.salesman_id
where s.commission>0.12 and c.city<>s.city
```

**Output:**

<img width="873" height="627" alt="image" src="https://github.com/user-attachments/assets/dfa21ea7-cb20-48eb-89bc-90b55be837c7" />



**Question 8**
---

<img width="886" height="768" alt="image" src="https://github.com/user-attachments/assets/3538cc8e-2d32-44db-aa7f-8f706117a814" />


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**

<img width="856" height="474" alt="image" src="https://github.com/user-attachments/assets/b87cc983-13fa-4208-ba5d-b6cd051ff4a7" />



**Question 9**
---

<img width="901" height="623" alt="image" src="https://github.com/user-attachments/assets/0c819654-17e0-4197-b4cc-45239aa708f8" />

```sql
SELECT s.name AS Salesman, c.cust_name, s.city
FROM salesman s
JOIN customer c
  ON s.city = c.city;

```

**Output:**

<img width="870" height="633" alt="image" src="https://github.com/user-attachments/assets/11fb91fb-1da5-435a-8c4c-bbe27f5b62f8" />



**Question 10**
---

<img width="856" height="736" alt="image" src="https://github.com/user-attachments/assets/85ce7fbb-f6d0-4329-8697-6b8bdbcaf975" />


```sql
SELECT p.first_name AS patient_name,
       t.*
FROM patients p
INNER JOIN test_results t
  ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';

```

**Output:**

<img width="884" height="420" alt="image" src="https://github.com/user-attachments/assets/6875aed1-59e7-464e-882c-6c96b52a9dee" />

GREADE:




## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
