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


<img width="1057" height="362" alt="image" src="https://github.com/user-attachments/assets/ba9a9669-fb56-4cf5-9e75-274771a59fb3" />


```sql
SELECT * 
FROM CUSTOMERS 
WHERE ADDRESS = 'Delhi' AND AGE < 30
ORDER BY ID;
```

**Output:**



<img width="1247" height="422" alt="image" src="https://github.com/user-attachments/assets/f4388897-f90c-4f46-99a0-e28db6db03a6" />


**Question 2**
---

  


<img width="1063" height="562" alt="image" src="https://github.com/user-attachments/assets/f53b27e2-63a2-437a-9866-027696985d6b" />


```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);
```

**Output:**




<img width="448" height="525" alt="image" src="https://github.com/user-attachments/assets/2aeaf949-0889-4364-8bec-9850833fbd80" />


**Question 3**
---



<img width="1212" height="531" alt="image" src="https://github.com/user-attachments/assets/08ac6988-0820-4271-a06b-938acd470ed2" />



```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM ORDERS
WHERE salesman_id IN (
    SELECT salesman_id 
    FROM SALESMAN 
    WHERE city = 'New York'
);
```

**Output:**

<img width="1288" height="536" alt="image" src="https://github.com/user-attachments/assets/efb19365-77dd-4518-b37b-2060b27690fe" />


**Question 4**
---


<img width="1042" height="673" alt="image" src="https://github.com/user-attachments/assets/5995a683-f0bb-4f9e-abaf-edfc10bcd82e" />




```sql
SELECT * 
FROM CUSTOMERS 
WHERE SALARY > 4500;
```

**Output:**

<img width="1250" height="500" alt="image" src="https://github.com/user-attachments/assets/7720df99-899e-43e8-aaa5-9afce372761b" />


**Question 5**
---


<img width="1272" height="390" alt="image" src="https://github.com/user-attachments/assets/c2b9c4b5-e142-4fca-b740-aa8b2bfeac70" />


```sql
SELECT student_id, student_name, subject, grade
FROM GRADES
WHERE (subject, grade) IN (
    SELECT subject, MIN(grade)
    FROM GRADES
    GROUP BY subject
);
```

**Output:**




<img width="1297" height="512" alt="image" src="https://github.com/user-attachments/assets/c7af6910-a5e0-4808-a45b-86e7500441cd" />


**Question 6**
---



<img width="1270" height="530" alt="image" src="https://github.com/user-attachments/assets/585f2170-7021-42f2-9e0f-ddf89ca1583a" />


```sql
SELECT ord_no AS ord_no, purch_amt, ord_date AS ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id 
    FROM salesman 
    WHERE name = 'Paul Adam'
);
```

**Output:**


<img width="1267" height="461" alt="image" src="https://github.com/user-attachments/assets/884ed019-3dd6-4dfc-8ebe-6002076d9b4c" />


**Question 7**
---

<img width="1082" height="363" alt="image" src="https://github.com/user-attachments/assets/4652cfc1-7ba9-4282-ab92-3f935b158c56" />


```sql
SELECT * 
FROM CUSTOMERS 
WHERE SALARY > 1500;
```

**Output:**

<img width="1245" height="641" alt="image" src="https://github.com/user-attachments/assets/494bc270-04c9-4893-b368-7acfb5af59e0" />


**Question 8**
---


<img width="967" height="355" alt="image" src="https://github.com/user-attachments/assets/5f2c32bd-bd4b-4a06-a065-38163c5d8c52" />


```sql
SELECT * 
FROM CUSTOMERS 
WHERE AGE < 30;
```

**Output:**

<img width="1248" height="653" alt="image" src="https://github.com/user-attachments/assets/be978100-d04c-4b95-ada0-043b3dd27bae" />


**Question 9**
---

<img width="1203" height="495" alt="image" src="https://github.com/user-attachments/assets/eba32695-6095-4061-888c-30b62c56825d" />


```sql
SELECT ord_no AS ord_no, purch_amt, ord_date AS ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id 
    FROM salesman 
    WHERE city = 'New York'
);
```

**Output:**

<img width="1275" height="518" alt="image" src="https://github.com/user-attachments/assets/0a2f50ac-2f9b-42e2-b3e6-7b3791549cab" />


**Question 10**
---

<img width="1036" height="292" alt="image" src="https://github.com/user-attachments/assets/70563831-53e6-413c-9455-ad2c4b9b8a39" />


```sql
SELECT medication_id AS medic, medication_name, dosage
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage) 
    FROM Medications
);
```

**Output:**

<img width="953" height="477" alt="image" src="https://github.com/user-attachments/assets/49f1b3d2-f221-43f6-9c69-b8517f112ca7" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
