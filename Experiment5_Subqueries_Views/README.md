# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="884" height="681" alt="image" src="https://github.com/user-attachments/assets/9c662b56-44b5-4b57-abd3-443bbe1893bc" />

```sql
SELECT g.student_name, g.grade
FROM grades g
WHERE grade = (
    SELECT MAX(grade)
    FROM grades
    WHERE subject = g.subject
);

```

**Output:**

<img width="875" height="439" alt="image" src="https://github.com/user-attachments/assets/42e54fc3-e5ca-457b-bf39-6d54afffe906" />


**Question 2**
---
<img width="832" height="506" alt="image" src="https://github.com/user-attachments/assets/e5237e9e-69e1-44e2-9782-a3761a9d3fc6" />


```sql
select o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id
from orders o
join salesman s on o.salesman_id=s.salesman_id
where s.city='New York'

```

**Output:**
<img width="882" height="471" alt="image" src="https://github.com/user-attachments/assets/ec9c658d-72a4-42c4-bb84-e3bf43eea05e" />

**Question 3**
---
<img width="904" height="757" alt="image" src="https://github.com/user-attachments/assets/6fbf1375-92b8-48b3-8225-53fb5698cecb" />
```sql
SELECT *FROM CUSTOMERS
WHERE salary > 1500;
```

**Output:**

<img width="873" height="612" alt="image" src="https://github.com/user-attachments/assets/940bd59e-985a-49df-a129-32a9c6282a0a" />


**Question 4**
---
<img width="860" height="679" alt="image" src="https://github.com/user-attachments/assets/4e5bde04-98a1-41b4-ad88-bafd8f0efb2a" />


```sql
SELECT * FROM CUSTOMERS
WHERE salary < 2500;
```

**Output:**
<img width="1247" height="435" alt="image" src="https://github.com/user-attachments/assets/99b618da-a642-4982-8597-f1ce065f0526" />


**Question 5**
---
<img width="1263" height="499" alt="image" src="https://github.com/user-attachments/assets/79d775f2-843e-4b65-9f33-966e755d745c" />


```sql
SELECT grade, COUNT(*)
FROM customer

where  grade > (
      SELECT AVG(grade)
      FROM customer
      WHERE city = 'New York'
  )
group by grade;

```

**Output:**
<img width="1045" height="343" alt="image" src="https://github.com/user-attachments/assets/d67776f0-4c65-43e6-80fa-d7323cd0255d" />


**Question 6**
---
<img width="1226" height="804" alt="image" src="https://github.com/user-attachments/assets/b2b8ea0d-0a82-4c79-b943-0c057693ca68" />

```sql
SELECT o.ord_no,
       o.purch_amt,
       o.ord_date,
       o.customer_id,
       o.salesman_id
FROM orders o
JOIN salesman s
  ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**
<img width="1260" height="482" alt="image" src="https://github.com/user-attachments/assets/525735f4-e000-4694-9ec8-40083f8a1297" />

**Question 7**
---
<img width="1216" height="645" alt="image" src="https://github.com/user-attachments/assets/84e7d01a-34d3-49cb-8ba4-800fa4c74a38" />


```sql
SELECT ord_no,
       purch_amt,
       ord_date,
       customer_id,
       salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);

```

**Output:**
<img width="1255" height="459" alt="image" src="https://github.com/user-attachments/assets/3026c869-b480-4254-b6e8-a2b418faef3e" />

**Question 8**
---
<img width="1193" height="708" alt="image" src="https://github.com/user-attachments/assets/083e5847-ae48-4498-8f56-270a291de635" />
```sql
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c 
  ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

<img width="670" height="457" alt="image" src="https://github.com/user-attachments/assets/69307fb6-8988-4408-8b52-e329c9dc6cb7" />


**Question 9**
---
<img width="881" height="667" alt="image" src="https://github.com/user-attachments/assets/d1a1586a-1515-47ac-8dbf-74ec83100724" />

```sql
SELECT g.*
FROM grades g
WHERE grade = (
    SELECT MIN(grade)
    FROM grades
    WHERE subject = g.subject
);

```

**Output:**
<img width="904" height="433" alt="image" src="https://github.com/user-attachments/assets/c2fb78b5-1aa2-4eb7-9b67-2812422e8929" />



**Question 10**
---
<img width="866" height="555" alt="image" src="https://github.com/user-attachments/assets/c4697d64-3e45-4c92-b430-9e4cb5e940d9" />


```sql
SELECT ord_no, 
       purch_amt, 
       ord_date, 
       customer_id, 
       salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM orders
    WHERE customer_id = 3007
);

```

**Output:**

<img width="860" height="431" alt="image" src="https://github.com/user-attachments/assets/bbe0316a-cb27-4efc-86d8-06135eb6a64f" />

GRADE:
<img width="1377" height="88" alt="image" src="https://github.com/user-attachments/assets/ea0c2a19-2a06-4420-82f7-012de2e5ff09" />

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
