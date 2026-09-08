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

<img width="1217" height="505" alt="image" src="https://github.com/user-attachments/assets/73bfa948-1564-4032-a5b1-51affb4dd26b" />


```sql
SELECT
s.name,
c.cust_name,
c.city,
c.grade,
c.salesman_id
FROM Salesman s
LEFT JOIN Customer c ON c.salesman_id=s.salesman_id;


```

**Output:**




<img width="1263" height="750" alt="image" src="https://github.com/user-attachments/assets/388b9783-b654-4ee3-ae89-77e72f89f082" />


**Question 2**
---


<img width="1275" height="622" alt="image" src="https://github.com/user-attachments/assets/923afdf5-0909-4549-a1a7-f51263ffb0fb" />


```sql
SELECT
c.cust_name,
c.city,
c.grade,
s.name AS Salesman,
s.city
FROM customer c
INNER JOIN salesman s ON c.salesman_id=s.salesman_id
ORDER BY c.customer_id ASC;
```

**Output:**






<img width="1252" height="756" alt="image" src="https://github.com/user-attachments/assets/f809be4b-2688-4bf5-a21a-757d6553191b" />


**Question 3**
---



<img width="1257" height="632" alt="image" src="https://github.com/user-attachments/assets/fbc5553c-71df-42ea-bc88-846329537054" />


```sql
SELECT
c.cust_name AS "Customer Name",
c.city,
s.name AS Salesman,
s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id=s.salesman_id;
```

**Output:**




<img width="1275" height="792" alt="image" src="https://github.com/user-attachments/assets/6cc2c2de-16ea-491d-9b47-50e62f4400de" />


**Question 4**
---


<img width="1258" height="200" alt="image" src="https://github.com/user-attachments/assets/294d5df3-3397-46e9-81c4-99b1f75d1a08" />


```sql
SELECT
c.cust_name,
o.ord_no,
o.ord_date,
o.purch_amt
FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id
WHERE o.purch_amt>1000;
```

**Output:**

<img width="1285" height="701" alt="image" src="https://github.com/user-attachments/assets/5f2b206a-bafb-4524-9f9f-cfb0878923fc" />


**Question 5**
---



<img width="1203" height="797" alt="image" src="https://github.com/user-attachments/assets/a66e208e-e952-40d2-915e-56e83c778ae3" />


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
LEFT JOIN orders o ON c.customer_id=o.customer_id
LEFT JOIN salesman s ON c.salesman_id=s.salesman_id;

```

**Output:**






<img width="1258" height="797" alt="image" src="https://github.com/user-attachments/assets/a4e9ae8c-2b85-4d71-9bdd-bcc750ba613a" />


**Question 6**
---




<img width="1266" height="802" alt="image" src="https://github.com/user-attachments/assets/bb4fe2be-a42a-4458-94af-fd30862eed2d" />


```sql
SELECT
o.ord_no,
o.purch_amt,
o.ord_date,
c.cust_name,
c.city AS "customer_city",
c.grade,
s.name AS "salesman_name",
s.city AS "salesman_city",
s.commission
FROM customer c
INNER JOIN orders o ON c.customer_id=o.customer_id
INNER JOIN salesman s ON c.salesman_id=s.salesman_id;

```

**Output:**



<img width="1262" height="791" alt="image" src="https://github.com/user-attachments/assets/7b1f45bf-26f8-43da-a295-648eaf6330ec" />


**Question 7**
---



<img width="1283" height="607" alt="image" src="https://github.com/user-attachments/assets/8f111226-c585-43b0-be6a-f9dee03dab90" />


```sql
SELECT
c.cust_name AS "Customer Name",
c.city,
s.name AS Salesman,
s.city,
s.commission
FROM customer c
INNER JOIN salesman s ON c.salesman_id=s.salesman_id
WHERE c.city!=s.city AND s.commission>0.12;
```

**Output:**






<img width="1268" height="702" alt="image" src="https://github.com/user-attachments/assets/070258ad-1504-4d72-9a1e-f4c6d5be19cc" />


**Question 8**
---





<img width="1242" height="515" alt="image" src="https://github.com/user-attachments/assets/7dc942f9-c1e6-4c96-9e26-eeccc25d1436" />


```sql
SELECT
n.nurse_id,
n.first_name,
n.last_name,
d.department_id
FROM NURSES n 
INNER JOIN DEPARTMENTS d ON n.department_id=d.department_id
WHERE d.department_name='Pediatrics';

```

**Output:**



<img width="1280" height="475" alt="image" src="https://github.com/user-attachments/assets/d6717c85-e93c-4b29-889a-84f113911c73" />





**Question 9**
---


<img width="1276" height="598" alt="image" src="https://github.com/user-attachments/assets/d78a0798-4854-42b3-9e34-e1fb45e6019d" />


```sql
SELECT
p.first_name,
s.*
FROM PATIENTS p
INNER JOIN SURGERIES s ON p.patient_id=s.patient_id
WHERE p.date_of_birth > '1990-01-01';

```

**Output:**



<img width="1272" height="488" alt="image" src="https://github.com/user-attachments/assets/dcfd7c64-85b0-4bdd-94ef-d04dbea576f8" />


**Question 10**
---



<img width="1195" height="683" alt="image" src="https://github.com/user-attachments/assets/552a384b-f248-442d-a36a-e0204d3b59ea" />


```sql
SELECT
p.*
FROM PATIENTS p
INNER JOIN TEST_RESULTS t ON p.patient_id=t.patient_id 
WHERE test_date BETWEEN  '2024-03-01' and '2024-03-31';


```

**Output:**





<img width="1287" height="483" alt="image" src="https://github.com/user-attachments/assets/5baa56cc-c8e4-4d9a-a480-59c6f1a103cd" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
