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
<img width="1043" height="222" alt="image" src="https://github.com/user-attachments/assets/9a34e326-240a-4eef-8ead-2980660a5b78" />


```sql
SELECT 
Medication,
AVG(Dosage) AS AvgDosage
FROM Prescriptions
GROUP BY Medication;
```

**Output:**

<img width="587" height="805" alt="image" src="https://github.com/user-attachments/assets/c099d3b6-c411-4d83-900f-4c264f9ebc6a" />


**Question 2**
---
<img width="1086" height="237" alt="image" src="https://github.com/user-attachments/assets/75b1e418-2c1d-4c07-b5b8-a62059f32133" />


```sql
SELECT
Gender,
COUNT(PatientID) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**



<img width="651" height="412" alt="image" src="https://github.com/user-attachments/assets/eae5ceb5-9ff0-4931-b231-8364e3398519" />


**Question 3**
---



<img width="565" height="291" alt="image" src="https://github.com/user-attachments/assets/3f89bb9b-92cc-4752-9791-f2bf1f9ba6dd" />


```sql
SELECT
InsuranceCompany,
COUNT(PatientID) AS TotalPatients
FROM INsurance
GROUP BY InsuranceCompany;
```

**Output:**




<img width="790" height="736" alt="image" src="https://github.com/user-attachments/assets/d8130e04-68a5-41ec-94cd-903dba4f3a7e" />



**Question 4**
---



<img width="762" height="476" alt="image" src="https://github.com/user-attachments/assets/b49db609-761a-42c0-8f26-1aaab55d1b85" />


```sql
SELECT
SUM(income) AS total_income
FROM employee
WHERE age>=40;
```

**Output:**





<img width="557" height="365" alt="image" src="https://github.com/user-attachments/assets/cfc09033-554c-4f44-bb8b-e3573e0b1330" />


**Question 5**
---





<img width="573" height="493" alt="image" src="https://github.com/user-attachments/assets/2d90a12c-c04e-4a1e-a761-3263e0049d77" />


```sql
SELECT
MAX(purch_amt) AS MAXIMUM
FROM orders
ORDER BY MAXIMUM DESC LIMIT 1;

```

**Output:**





<img width="542" height="381" alt="image" src="https://github.com/user-attachments/assets/f17e6402-6cbd-4026-a5dd-b953fabbdf35" />


**Question 6**
---



<img width="658" height="257" alt="image" src="https://github.com/user-attachments/assets/a0660d6c-0e4a-4fc9-a328-17d921ec7988" />


```sql
SELECT
COUNT(id) AS employees_in_california
FROM employee
WHERE city='California';
```

**Output:**





<img width="687" height="362" alt="image" src="https://github.com/user-attachments/assets/7ac2317a-9450-4775-b219-df7911060b49" />


**Question 7**
---




<img width="657" height="268" alt="image" src="https://github.com/user-attachments/assets/f17ce041-0e08-4afc-b6be-1450def4302c" />


```sql
SELECT
MIN(purch_amt) AS MINIMUM
FROM orders
ORDER BY purch_amt DESC LIMIT 1;
```

**Output:**





<img width="455" height="371" alt="image" src="https://github.com/user-attachments/assets/00159a90-a37e-404c-8342-9c861880d380" />


**Question 8**
---




<img width="1196" height="321" alt="image" src="https://github.com/user-attachments/assets/67295c16-55a3-4616-8a68-17062cde9dc1" />


```sql
SELECT
category_id,
product_name,
MAX(price) AS Price
FROM products
GROUP BY category_id
HAVING Price>15;
```

**Output:**






<img width="853" height="460" alt="image" src="https://github.com/user-attachments/assets/863c7c45-144b-4be1-9033-070f7c71909d" />


**Question 9**
---




<img width="1227" height="262" alt="image" src="https://github.com/user-attachments/assets/db4d1057-75f7-4c40-b861-68007a52f0eb" />


```sql
SELECT 
(age/5)*5 AS age_group,
SUM(salary)
FROM customer1
GROUP BY age_group
HAVING SUM(salary)>5000;


```

**Output:**






<img width="590" height="417" alt="image" src="https://github.com/user-attachments/assets/aa970ddd-a7ed-4489-a8a2-150d253d878f" />


**Question 10**
---




<img width="1226" height="288" alt="image" src="https://github.com/user-attachments/assets/9c392f86-e667-477f-9b4d-633839bbd945" />


```sql
SELECT 
category_id,
COUNT(product_name) AS "COUNT"
FROM products
GROUP BY category_id
HAVING category_id>2;
```

**Output:**






<img width="621" height="405" alt="image" src="https://github.com/user-attachments/assets/1f2c0712-eda2-4de8-bfaa-ce456519ecde" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
