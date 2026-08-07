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


<img width="1427" height="528" alt="Screenshot 2026-08-07 100646" src="https://github.com/user-attachments/assets/f59d413a-cc99-46ea-af9b-b130354f9196" />


```sql
INSERT INTO Books(ISBN, Title, Author, Publisher, Year)
VALUES('978-1234567890', 'Data Science Essentials', 'Jane Doe', 'TechBooks', '2024');
```



**Output:**


<img width="1231" height="328" alt="Screenshot 2026-08-07 100654" src="https://github.com/user-attachments/assets/4e7dc1e9-c290-4ff2-9a41-62ffd37643f7" />





**Question 2**





<img width="1422" height="751" alt="Screenshot 2026-08-07 100704" src="https://github.com/user-attachments/assets/7d594a43-5f46-46ca-899c-63333e978d23" />





```sql
ALTER TABLE Student_details
ADD mobilenumber number;
```


**Output:**

<img width="1222" height="458" alt="Screenshot 2026-08-07 100711" src="https://github.com/user-attachments/assets/b8c45bd1-7b7d-47e2-bd84-028e1fb3e200" />


**Question 3**
---


<img width="1426" height="756" alt="Screenshot 2026-08-07 100720" src="https://github.com/user-attachments/assets/648c06e5-5b98-45ca-93e3-7b0659459d28" />




```sql


CREATE TABLE products(
product_id INTEGER PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL(10,2) NOT NULL,
discount DECIMAL(10,2) DEFAULT(0) NOT NULL,
CHECK(list_price>=discount AND discount>=0 AND list_price >=0)
);




```

**Output:**


<img width="1327" height="396" alt="Screenshot 2026-08-07 100731" src="https://github.com/user-attachments/assets/c100160e-2b7a-4839-aab7-f1cd59c5b484" />



**Question 4**




<img width="1390" height="720" alt="Screenshot 2026-08-07 100741" src="https://github.com/user-attachments/assets/57056965-b7cb-4ed9-85b3-6ece841c4e93" />



```sql

CREATE TABLE Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT
);

```

**Output:**

<img width="1266" height="496" alt="Screenshot 2026-08-07 100751" src="https://github.com/user-attachments/assets/35948b39-3491-4b53-9472-ea97e93e38b3" />


**Question 5**


<img width="1411" height="652" alt="Screenshot 2026-08-07 100800" src="https://github.com/user-attachments/assets/32b11d1b-9a7e-4aaa-80d5-8fca26a01acd" />


```sql

CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
Amount REAL CHECK(Amount>0),
DueDate DATE CHECK(DueDate>InvoiceDate),
OrderID INTEGER REFERENCES Orders(OrderID)
;

```

**Output:**

<img width="1235" height="360" alt="Screenshot 2026-08-07 100810" src="https://github.com/user-attachments/assets/fc3f50fb-daf4-4090-a221-ff55f44d5baa" />


**Question 6**


<img width="1426" height="765" alt="Screenshot 2026-08-07 100820" src="https://github.com/user-attachments/assets/f032ff54-0e16-4d98-9e45-994153864f48" />




```sql

INSERT INTO Books(ISBN,Title,Author,Publisher, Year)
VALUES('978-1234567890', 'Introduction to AI', 'John Doe' ,'',''),
('978-9876543210', 'Deep Learning', 'Jane Doe', 'TechPress' , '2022'),
('978-1122334455', 'Cybersecurity Essentials', 'Alice Smith',' ','2021');

```

**Output:**

<img width="1292" height="397" alt="Screenshot 2026-08-07 100830" src="https://github.com/user-attachments/assets/b3a2190a-7c86-4da9-8160-e2893a272845" />


**Question 7**

<img width="1442" height="757" alt="Screenshot 2026-08-07 100840" src="https://github.com/user-attachments/assets/e70d5896-3826-4a11-b76e-139382593a0c" />


```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT CHECK(LENGTH(icom_id) == 4),
FOREIGN KEY(icom_id) REFERENCES company(com_id) ON UPDATE CASCADE ON DELETE CASCADE

);



```

**Output:**

<img width="1242" height="431" alt="Screenshot 2026-08-07 100848" src="https://github.com/user-attachments/assets/1080f35f-4291-401a-b9d7-be85e0a87e22" />


**Question 8**

<img width="1408" height="593" alt="Screenshot 2026-08-07 100856" src="https://github.com/user-attachments/assets/046f2156-f067-40ad-ae55-4fc555731de8" />



```sql

INSERT INTO EMPLOYEE(EmployeeID, Name,Department, Salary)
SELECT EmployeeID, Name, Department, Salary
FROM Former_employees;

```

**Output:**

<img width="1245" height="385" alt="Screenshot 2026-08-07 100905" src="https://github.com/user-attachments/assets/435a6716-d9d7-423a-827a-46277c1ea483" />




**Question 9**


<img width="1427" height="752" alt="Screenshot 2026-08-07 100914" src="https://github.com/user-attachments/assets/58482507-16ea-47e8-847a-cc4129ccfe45" />


```sql

ALTER TABLE customer
RENAME city TO location;


```

**Output:**

<img width="1231" height="427" alt="Screenshot 2026-08-07 100923" src="https://github.com/user-attachments/assets/5932cc0d-99ca-4d08-a3c4-da65e17787b3" />




**Question 10**

<img width="1410" height="672" alt="Screenshot 2026-08-07 100935" src="https://github.com/user-attachments/assets/feedbf60-de63-4647-920e-2e248ae60ad5" />



```sql

CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER REFERENCES Employees(EmployeeID),
BonusAmount REAL CHECK(BonusAmount>0),
BonusDate DATE,
Reason TEXT NOT NULL
):

```

**Output:**

<img width="1273" height="438" alt="Screenshot 2026-08-07 100945" src="https://github.com/user-attachments/assets/19c4d79f-7552-42e1-be1f-5489cf67f54d" />



**MODULE-1 SEB GRADES**


<img width="1882" height="863" alt="Screenshot 2026-08-07 100958" src="https://github.com/user-attachments/assets/9d737236-4352-43ed-a9d5-02f02f0dcda1" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
