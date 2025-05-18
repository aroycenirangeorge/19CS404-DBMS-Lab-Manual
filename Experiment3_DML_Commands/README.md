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
![image](https://github.com/user-attachments/assets/b5e70542-5c59-435a-ae37-f5806180d4d6)


```sql
UPDATE SALES SET total_sell_price=quantity*sell_price WHERE product_id=10
```

**Output:**

![image](https://github.com/user-attachments/assets/5c2b7d38-0707-437c-803a-08b15e0a40a0)


**Question 2**
---
![image](https://github.com/user-attachments/assets/b85c43f7-1856-4033-a30a-fb9b9de9a3d7)

```sql
UPDATE Products SET product_name='Premium Bread' WHERE product_id=5
```

**Output:**

![image](https://github.com/user-attachments/assets/4e3c9eb3-1546-4670-beeb-671f3ea961ae)

**Question 3**
---
![image](https://github.com/user-attachments/assets/e8316804-a477-43c6-b16d-f8adb5642ff1)

```sql
UPDATE Products SET category='Household' WHERE product_name LIKE '%Detergent%'
```

**Output:**

![image](https://github.com/user-attachments/assets/a4b2e678-2823-4a2d-b620-df43203f711a)

**Question 4**
---
![image](https://github.com/user-attachments/assets/1fde20b2-bce3-40f2-bcbe-a45a419686ef)

```sql
UPDATE Suppliers SET address='58 Lakeview, Magnolia' WHERE supplier_id=5
```

**Output:**

![image](https://github.com/user-attachments/assets/f7e09c57-e434-453f-a3d1-17f6229605ec)

**Question 5**
---
![image](https://github.com/user-attachments/assets/911200a8-f2ba-4e0e-bfab-8de208774ae7)

```sql
UPDATE Employees SET
salary=salary+salary*0.25 WHERE department_id=40;
UPDATE Employees SET
salary=salary+salary*0.15 WHERE department_id=90;
UPDATE Employees SET
salary=salary+salary*0.10 WHERE department_id=110;
```

**Output:**

![image](https://github.com/user-attachments/assets/17aafeb2-7c03-4be1-afa1-fb43b3a96673)

**Question 6**
---
![image](https://github.com/user-attachments/assets/1bff943f-ca14-4807-8e9f-bd4a971f5e78)

```sql
DELETE FROM Customer WHERE AGENT_CODE = 'A003' OR AGENT_CODE = 'A008'
```

**Output:**

![image](https://github.com/user-attachments/assets/498ffe96-d00d-4fac-ac32-20b8addbcae8)

**Question 7**
---
![image](https://github.com/user-attachments/assets/b6dfba8a-ae51-4e69-9d47-5575e963c4a8)

```sql
DELETE FROM customer WHERE GRADE%2=1
```

**Output:**

![image](https://github.com/user-attachments/assets/1e86a555-616e-4eac-bc5a-575deaf00bdd)

**Question 8**
---
![image](https://github.com/user-attachments/assets/08c5fb5f-c4ef-4cac-9d2c-2b89cad007f5)

```sql
DELETE FROM Customer WHERE CUST_COUNTRY NOT IN ('UK','USA','Canada') AND GRADE>=3
```

**Output:**

![image](https://github.com/user-attachments/assets/40748436-7f27-44df-b275-0b2646c7df3d)

**Question 9**
---
![image](https://github.com/user-attachments/assets/18454a24-9483-4787-bad1-ed9c668a7269)

```sql
SELECT * FROM EmployeeInfo WHERE Address='Delhi(DEL)'
```

**Output:**

![image](https://github.com/user-attachments/assets/a17ea86f-8872-4551-a987-e2525c4b35b6)

**Question 10**
---
![image](https://github.com/user-attachments/assets/d87dd112-3a38-4b30-8fef-fd892e38c7b0)

```sql
SELECT * FROM EmployeePosition ORDER BY Salary DESC LIMIT 3
```

**Output:**

![image](https://github.com/user-attachments/assets/d9b54eec-3d63-4b67-bae2-b5892c942923)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
