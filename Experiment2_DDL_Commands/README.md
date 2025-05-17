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
---
**Question 1**
---
![image](https://github.com/user-attachments/assets/c30439c8-26bd-4989-ab87-ee7a4a09ff60)

```sql
CREATE TABLE Invoices(InvoiceID INT PRIMARY KEY, InvoiceDate DATE, DueDate DATE CHECK(DueDate>InvoiceDate), Amount REAL CHECK(Amount>0) )
```

**Output:**

![image](https://github.com/user-attachments/assets/be038b9f-6a4d-42d2-b0fd-023f49315db0)


**Question 2**
---
![image](https://github.com/user-attachments/assets/1915fe9b-7546-4884-b824-630208fe1102)

```sql
CREATE TABLE Tasks(TaskID INTEGER,TaskName TEXT,DueDate DATE)
```

**Output:**

![image](https://github.com/user-attachments/assets/29b7af26-6654-4679-8716-f1522796f407)


**Question 3**
---
![image](https://github.com/user-attachments/assets/f511f4b4-bf03-45c6-9f7e-170632d8882f)

```sql
CREATE TABLE ProjectAssignments(AssignmentID INTEGER, EmployeeID INTEGER, ProjectID INTEGER, AssignmentDate DATE NOT NULL, FOREIGN KEY (EmployeeID) references Employees(EmployeeID), FOREIGN KEY (ProjectID) references Projects(ProjectID))
```

**Output:**

![image](https://github.com/user-attachments/assets/51b71d35-56d6-45e6-89e1-e2bf13b1a63a)


**Question 4**
---
![image](https://github.com/user-attachments/assets/4a921999-333e-452a-8523-5ae47f0367b5)

```sql
CREATE TABLE item(item_id TEXT PRIMARY KEY, item_desc TEXT NOT NULL, rate INTEGER NOT NULL,icom_id TEXT CHECK(icom_id>4),FOREIGN KEY (icom_id) references company(com_id) ON UPDATE SET NULL ON DELETE SET NULL)
```

**Output:**

![image](https://github.com/user-attachments/assets/0aa9c37c-79df-40d4-9ea4-e084a13b248c)


**Question 5**
---
![image](https://github.com/user-attachments/assets/b473724b-a7f0-49c8-8305-2eeddac0ba66)

```sql
ALTER TABLE employee ADD department_id INTEGER;
ALTER TABLE employee ADD manager_id INTEGER DEFAULT NULL
```

**Output:**

![image](https://github.com/user-attachments/assets/e8556fc6-dd93-4149-8821-f1337c602563)


**Question 6**
---
![image](https://github.com/user-attachments/assets/25b57c14-bbcd-4223-b470-ef1a3f45d53a)


```sql
CREATE TABLE orders(ord_id TEXT CHECK(ord_id>4) NOT NULL,item_id TEXT NOT NULL, ord_date DATE, ord_qty INTEGER, cost INTEGER, PRIMARY KEY(item_id,ord_date))
```

**Output:**

![image](https://github.com/user-attachments/assets/863a2414-cc26-43f0-8387-b2316d64bb38)


**Question 7**
---
![image](https://github.com/user-attachments/assets/95d59999-14cf-439a-ad43-5a08046412e8)

```sql
CREATE TABLE Products(ProductID INT,ProductName CHAR NOT NULL,Price INT,StockQuantity INT,PRIMARY KEY(ProductID),UNIQUE(ProductName),CHECK(Price>0),CHECK(StockQuantity>0))
```

**Output:**

![image](https://github.com/user-attachments/assets/c9dfba89-7ac1-44d9-995f-28f9eed37029)


**Question 8**
---
![image](https://github.com/user-attachments/assets/de3796a5-7450-44c8-8900-eca16df82d62)

```sql
CREATE TABLE Employees(EmployeeID INTEGER,FirstName TEXT, LastName TEXT, HireDate DATE)
```

**Output:**

![image](https://github.com/user-attachments/assets/85a29fbc-bf9d-464a-8cdb-27d9256896e8)


**Question 9**
---
![image](https://github.com/user-attachments/assets/7cf814c9-6a9b-4f75-b834-a314fdb6816d)

```sql
ALTER TABLE customer ADD birth_date timestamp
```

**Output:**

![image](https://github.com/user-attachments/assets/eb9edd83-d6bb-4fbd-bb76-647fcc50384a)


**Question 10**
---
![image](https://github.com/user-attachments/assets/4c3fe9c4-da0d-477d-8332-9ad019040f24)

```sql
CREATE TABLE Orders(OrderID INT,OrderDate DATE NOT NULL, CustomerID INT, PRIMARY KEY(OrderID), FOREIGN KEY(CustomerID) REFERENCES Customers(CustomerID))
```

**Output:**

![image](https://github.com/user-attachments/assets/e3eb0569-3e7a-4db6-96c3-e3acdfed1ac3)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
