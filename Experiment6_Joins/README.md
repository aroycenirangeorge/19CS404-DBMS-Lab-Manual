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
![image](https://github.com/user-attachments/assets/33eaa085-300f-410c-a202-d27e62616027)

```sql
SELECT o.ord_no, 
       o.ord_date, 
       o.purch_amt, 
       c.cust_name AS [Customer Name], 
       c.grade, 
       s.name AS Salesman, 
       s.commission
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/b11f84f2-2424-45a2-9f2c-ac574b0035f0)

**Question 2**
---
![image](https://github.com/user-attachments/assets/5fe77526-1fa2-46cd-b98f-2cd0c894b7e0)

```sql
SELECT p.admission_date, s.surgery_date
FROM patients p
INNER JOIN surgeries s ON p.patient_id = s.patient_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/b15805b0-edf6-4760-98be-8796667db19d)

**Question 3**
---
![image](https://github.com/user-attachments/assets/1a78c59c-3e09-4179-ad93-22eea6dc466d)

```sql
SELECT p.*
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id
WHERE t.test_name IN ('Blood Test', 'Blood Pressure')
AND t.result NOT LIKE '%Normal%';
```

**Output:**

![image](https://github.com/user-attachments/assets/bf35d3ed-c9a1-483e-a836-50a0d4cdda4b)

**Question 4**
---
![image](https://github.com/user-attachments/assets/ed323dc5-f483-4949-b7d6-79ceeefab166)

```sql
SELECT c.cust_name, s.commission FROM Customer c LEFT JOIN Salesman s ON c.salesman_id=s.salesman_id
```

**Output:**

![image](https://github.com/user-attachments/assets/9dc74b92-b277-4aea-adff-535fcb76309f)

**Question 5**
---
![image](https://github.com/user-attachments/assets/72b8239a-7524-4202-a4d1-3813a270cae2)

```sql
SELECT s.name AS Salesman, c.cust_name, c.city FROM salesman s JOIN customer c ON s.city=c.city
```

**Output:**

![image](https://github.com/user-attachments/assets/f72a15d9-af54-4641-b8d0-aa603d34fe98)

**Question 6**
---
![image](https://github.com/user-attachments/assets/65073038-455f-49c1-984f-3d023618afb4)

```sql
SELECT p.first_name AS patient_name FROM PATIENTS p INNER JOIN TEST_RESULTS t ON p.patient_id=t.patient_id WHERE t.test_name IN ('Blood Pressure')
```

**Output:**

![image](https://github.com/user-attachments/assets/07fe5bdd-b13a-4d0c-9a77-2f95aafa1e26)

**Question 7**
---
![image](https://github.com/user-attachments/assets/6f76cc4d-1b5b-450b-8c23-f5a8ff4f57f9)

```sql
SELECT c.cust_name AS [Customer Name], c.city, s.name AS Salesman, s.commission FROM customer c JOIN salesman s ON c.salesman_id=s.salesman_id
```

**Output:**

![image](https://github.com/user-attachments/assets/c1fd7b8e-e935-4fd1-b8c5-8cc8f30bef9f)

**Question 8**
---
![image](https://github.com/user-attachments/assets/e2882ab6-004a-414b-81f2-fbe1c4cade8a)

```sql
SELECT c.cust_name as [Customer Name], c.city, s.name as Salesman, s.city, s.commission FROM customer c JOIN salesman s ON c.salesman_id=s.salesman_id WHERE c.city!=s.city AND commission>0.12
```

**Output:**

![image](https://github.com/user-attachments/assets/095b9386-7ccf-4c38-b78b-f341374c3de3)

**Question 9**
---
![image](https://github.com/user-attachments/assets/a42fca7e-985e-4569-b614-793e86797cad)

```sql
SELECT c.cust_name, c.city, c.grade, s.name AS Salesman, s.city FROM customer c JOIN salesman s ON c.salesman_id=s.salesman_id ORDER BY c.customer_id
```

**Output:**
![image](https://github.com/user-attachments/assets/90a1b4a8-0194-4835-8f91-7b664bc4868c)


**Question 10**
---
![image](https://github.com/user-attachments/assets/8d075be2-c943-4cd5-a68d-4972f6ef7ed7)

```sql
SELECT c.cust_name, o.ord_no, o.ord_date, o.purch_amt FROM CUSTOMER c LEFT JOIN ORDERS o ON c.customer_id=o.customer_id
```

**Output:**

![image](https://github.com/user-attachments/assets/bcd11aca-cc32-4cac-a106-7852c6d7f2c8)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
