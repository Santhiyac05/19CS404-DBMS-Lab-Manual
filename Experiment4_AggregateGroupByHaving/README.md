# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="853" height="650" alt="image" src="https://github.com/user-attachments/assets/d7ec21df-c965-464d-8aa7-bf773db417e6" />


```sql
SELECT 
    DATE(AppointmentDateTime) AS AppointmentDate,
    COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DATE(AppointmentDateTime)
ORDER BY AppointmentDate;
```

**Output:**
<img width="839" height="703" alt="image" src="https://github.com/user-attachments/assets/57846a2c-aa28-4eb4-80e2-fcd7f4769670" />



**Question 2**
---
<img width="593" height="698" alt="image" src="https://github.com/user-attachments/assets/1dd96f10-d852-49e7-9b6c-82a4783d384d" />


```sql
SELECT PatientID,count(*) AS  TotalAppointments
FROM  Appointments 
group by PatientID 
order by patientID;
```

**Output:**

<img width="743" height="707" alt="image" src="https://github.com/user-attachments/assets/e7e171aa-e307-4552-a60f-15b21079622b" />


**Question 3**
---
<img width="643" height="562" alt="image" src="https://github.com/user-attachments/assets/81956119-fe31-49a7-9efd-9c392f745f1f" />


```sql
SELECT 
    STRFTIME('%Y', ValidityPeriod) AS ValidityYear,
    COUNT(DISTINCT PatientID) AS TotalPatients
FROM Insurance
GROUP BY STRFTIME('%Y', ValidityPeriod)
ORDER BY ValidityYear;
```

**Output:**

<img width="784" height="470" alt="image" src="https://github.com/user-attachments/assets/ee3ff507-513b-482e-b3bb-579503336a18" />


**Question 4**
---
<img width="788" height="526" alt="image" src="https://github.com/user-attachments/assets/b5aaa9db-c6ce-401c-bd88-5f7ee1d516a3" />


```sql
SELECT COUNT(DISTINCT salesman_id) AS COUNT
FROM orders;
```

**Output:**
<img width="835" height="366" alt="image" src="https://github.com/user-attachments/assets/98659843-1a6d-4c21-969e-03e74abb4e37" />



**Question 5**
---
<img width="808" height="561" alt="image" src="https://github.com/user-attachments/assets/1c5c326c-46d5-41c5-96ec-66322ed38584" />


```sql
SELECT SUM(inventory) AS total_available_amount
FROM fruits
WHERE price > 0.5;
```

**Output:**

<img width="746" height="376" alt="image" src="https://github.com/user-attachments/assets/aef4f4ea-18fb-4c18-afd6-1e685a2dc98e" />


**Question 6**
---
<img width="748" height="457" alt="image" src="https://github.com/user-attachments/assets/58207a9c-57d8-4b1a-88bb-f14e63ff2c1a" />


```sql
SELECT SUM(income) AS total_income
FROM  employee
WHERE age >= 40; 
```

**Output:**

<img width="817" height="388" alt="image" src="https://github.com/user-attachments/assets/fa3ddfda-70b1-4362-9543-b4a84b2496a4" />


**Question 7**
---
<img width="859" height="540" alt="image" src="https://github.com/user-attachments/assets/bcdd88fa-9c46-44f2-b677-9c7676187cb3" />


```sql
SELECT COUNT(*) AS COUNT
FROM customer
WHERE city <>'Noida';
```

**Output:**
<img width="741" height="389" alt="image" src="https://github.com/user-attachments/assets/5f4d5585-94c9-4814-9c29-05c947c4a326" />



**Question 8**
---
<img width="833" height="556" alt="image" src="https://github.com/user-attachments/assets/f5bd3baa-afe1-443f-a53f-987b85ebb9bb" />


```sql
SELECT 
    occupation,
    SUM(workhour) AS "SUM(workhour)"
FROM employee1
GROUP BY occupation
HAVING SUM(workhour) > 20;
```

**Output:**

<img width="739" height="526" alt="image" src="https://github.com/user-attachments/assets/e19b869c-1c75-4b2f-8cb1-d91fe56850e4" />


**Question 9**
---
<img width="849" height="525" alt="image" src="https://github.com/user-attachments/assets/0053fdc0-a140-4a03-89e2-f7c119f9422c" />


```sql
SELECT 
    jdate,
    MAX(workhour) AS "MAX(workhour)"
FROM employee1
GROUP BY jdate
HAVING MAX(workhour) > 12;
```

**Output:**

<img width="780" height="470" alt="image" src="https://github.com/user-attachments/assets/818690c3-72d1-499e-9a37-1f488827f8f0" />


**Question 10**
---
<img width="870" height="531" alt="image" src="https://github.com/user-attachments/assets/8dd49165-78a2-4edb-8855-b5de0808ef10" />


```sql
SELECT 
    occupation,
    AVG(workhour) AS "AVG(workhour)"
FROM employee1
GROUP BY occupation
HAVING AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**

<img width="797" height="460" alt="image" src="https://github.com/user-attachments/assets/bbd092d0-1401-4cdd-95c4-536492fd2427" />

GRADES:

<img width="810" height="162" alt="image" src="https://github.com/user-attachments/assets/0126bf59-b53e-4267-969f-d440578edfb3" />

<img width="777" height="156" alt="image" src="https://github.com/user-attachments/assets/c5569742-8919-4a19-b9d0-18279650aeb8" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
