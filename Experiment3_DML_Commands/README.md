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
-- Paste Question 1 here


<img width="1231" height="626" alt="image" src="https://github.com/user-attachments/assets/be208fb0-7737-48a9-a842-687705406365" />




```sql
UPDATE Employees
SET salary=salary*2
WHERE job_ID LIKE "%MAN";
```

**Output:**

<img width="1220" height="427" alt="image" src="https://github.com/user-attachments/assets/fdadd4ae-f0c0-4c34-8412-4a2fc6460771" />


**Question 2**
---
-- Paste Question 2 here



<img width="1197" height="800" alt="image" src="https://github.com/user-attachments/assets/ba0b7953-737d-48dd-83bf-85caa62a2327" />





```sql
UPDATE SALES
SET sell_price=sell_price+3
WHERE product_id IN(
SELECT product_id 
FROM PRODUCTS
WHERE supplier_id=4
)
```

**Output:**

<img width="1238" height="456" alt="image" src="https://github.com/user-attachments/assets/81cafc24-81c9-46be-bb32-6e2cb9e9ad53" />


**Question 3**
---
-- Paste Question 3 here

<img width="1328" height="522" alt="image" src="https://github.com/user-attachments/assets/014e9064-ac2b-426b-88e0-530465fa2e65" />



```sql
UPDATE SALES
SET total_sell_price=quantity*sell_price
WHERE product_id=10;
```

**Output:**

<img width="1227" height="593" alt="image" src="https://github.com/user-attachments/assets/62d7998d-9b5f-4f13-9636-3ec95d9707c5" />


**Question 4**
---
-- Paste Question 4 here


<img width="1233" height="561" alt="image" src="https://github.com/user-attachments/assets/f3995393-8cd2-4a5d-bfd0-977874319caf" />


```sql
UPDATE Products
SET sell_price=sell_price*1.15
WHERE quantity<50 AND supplier_id=10;
```

**Output:**

<img width="1227" height="592" alt="image" src="https://github.com/user-attachments/assets/9e7fe117-0441-49e0-88d8-82fce87b8481" />


**Question 5**
---


<img width="1423" height="245" alt="image" src="https://github.com/user-attachments/assets/e5ea3b16-f52f-4e7f-b732-f2c7192f0d30" />


```sql
UPDATE products
SET product_name='Grapefruit'
WHERE product_id=4;
```

**Output:**


<img width="1225" height="327" alt="image" src="https://github.com/user-attachments/assets/89e23e07-2632-448a-bea4-a44667809586" />


**Question 6**
---

<img width="1402" height="500" alt="image" src="https://github.com/user-attachments/assets/18ff45c2-560f-477b-9f3e-5c90131d2c0c" />


```sql

DELETE FROM Customer
WHERE (GRADE>2 AND PAYMENT_AMT< (SELECT AVG(PAYMENT_AMT) FROM Customer) )OR OUTSTANDING_AMT>8000;
```

**Output:**

<img width="1230" height="755" alt="image" src="https://github.com/user-attachments/assets/35d6c5fe-8be2-4ad2-8230-be52f6fb236e" />




**Question 7**
---

<img width="1428" height="487" alt="image" src="https://github.com/user-attachments/assets/8fff7367-05ba-4899-9ad5-225f601061e9" />


```sql

DELETE FROM Customer
WHERE CUST_COUNTRY='UK' AND WORKING_AREA='London' AND GRADE<3;

```

**Output:**

<img width="1232" height="563" alt="image" src="https://github.com/user-attachments/assets/181245b7-a492-42c8-a24c-353ed9537f18" />


**Question 8**
---

<img width="1408" height="577" alt="image" src="https://github.com/user-attachments/assets/5dc7c52f-3d00-493c-9be4-3fabff469b6c" />


```sql

DELETE FROM Doctors
WHERE specialization IS NULL;

```

**Output:**

<img width="1218" height="750" alt="image" src="https://github.com/user-attachments/assets/cd44abd6-f957-45f0-b029-253f6387ed4f" />


**Question 9**
---

<img width="1102" height="653" alt="image" src="https://github.com/user-attachments/assets/ad991c70-3187-45a2-b51e-141fbbc6d2c8" />


```sql

DELETE FROM Surgeries
WHERE surgery_id=3 or surgeon_id=4;

```

**Output:**

<img width="1202" height="703" alt="image" src="https://github.com/user-attachments/assets/1ed3f372-7903-4069-a0da-66c37acff9c6" />


**Question 10**

---


<img width="1407" height="486" alt="image" src="https://github.com/user-attachments/assets/653e5e30-a506-421c-99ef-f8657a1cacb7" />


```sql

DELETE FROM Customer
WHERE GRADE%2=1;

```

**Output:**

<img width="1215" height="497" alt="image" src="https://github.com/user-attachments/assets/c510cedb-678a-4bb0-b527-504d7639a6a3" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
