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
--Create a table named Invoices with the following constraints:

InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
DueDate as DATE should be greater than the InvoiceDate.
Amount as REAL should be greater than 0.

```sql
CREATE TABLE Invoices(InvoiceID INT PRIMARY KEY, InvoiceDate DATE, DueDate DATE CHECK(DueDate>InvoiceDate), Amount REAL CHECK(Amount>0) )
```

**Output:**

![Output1](output.png)

**Question 2**
---
-- Create a table named Tasks with the following columns:

TaskID as INTEGER
TaskName as TEXT
DueDate as DATE

```sql
CREATE TABLE Tasks(TaskID INTEGER,TaskName TEXT,DueDate DATE)
```

**Output:**

![Output2](output.png)

**Question 3**
---
-- Create a table named ProjectAssignments with the following constraints:
AssignmentID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
ProjectID as INTEGER should be a foreign key referencing Projects(ProjectID).
AssignmentDate as DATE should be NOT NULL.

```sql
CREATE TABLE ProjectAssignments(AssignmentID INTEGER, EmployeeID INTEGER, ProjectID INTEGER, AssignmentDate DATE NOT NULL, FOREIGN KEY (EmployeeID) references Employees(EmployeeID), FOREIGN KEY (ProjectID) references Projects(ProjectID))
```

**Output:**

![Output3](output.png)

**Question 4**
---
-- Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should set NULL on updates and deletes.
item_desc and rate should not accept NULL.

```sql
CREATE TABLE item(item_id TEXT PRIMARY KEY, item_desc TEXT NOT NULL, rate INTEGER NOT NULL,icom_id TEXT CHECK(icom_id>4),FOREIGN KEY (icom_id) references company(com_id) ON UPDATE SET NULL ON DELETE SET NULL)
```

**Output:**

![Output4](output.png)

**Question 5**
---
-- Write an SQL query to add two new columns, department_id and manager_id, to the table employee with datatype of INTEGER. The manager_id column should have a default value of NULL.

```sql
ALTER TABLE employee ADD department_id INTEGER;
ALTER TABLE employee ADD manager_id INTEGER DEFAULT NULL
```

**Output:**

![Output5](output.png)

**Question 6**
---
--Create a new table named orders with the following specifications:
ord_id as TEXT with a length of 4.
item_id as TEXT.
ord_date as DATE.
ord_qty as INTEGER.
cost as INTEGER.
The primary key is a composite key consisting of item_id and ord_date.
ord_id and item_id should not accept NULL

```sql
CREATE TABLE orders(ord_id TEXT CHECK(ord_id>4) NOT NULL,item_id TEXT NOT NULL, ord_date DATE, ord_qty INTEGER, cost INTEGER, PRIMARY KEY(item_id,ord_date))
```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Create a table named Products with the following constraints:
ProductID as INTEGER should be the primary key.
ProductName as TEXT should be unique and not NULL.
Price as REAL should be greater than 0.
StockQuantity as INTEGER should be non-negative.

```sql
CREATE TABLE Products(ProductID INT,ProductName CHAR NOT NULL,Price INT,StockQuantity INT,PRIMARY KEY(ProductID),UNIQUE(ProductName),CHECK(Price>0),CHECK(StockQuantity>0))
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Create a table named Employees with the following columns:

EmployeeID as INTEGER
FirstName as TEXT
LastName as TEXT
HireDate as DATE

```sql
CREATE TABLE Employees(EmployeeID INTEGER,FirstName TEXT, LastName TEXT, HireDate DATE)
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Write a SQL query to add birth_date attribute as timestamp (datatype) in the table customer 

```sql
ALTER TABLE customer ADD birth_date timestamp
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Create a table named Orders with the following constraints:
OrderID as INTEGER should be the primary key.
OrderDate as DATE should be not NULL.
CustomerID as INTEGER should be a foreign key referencing Customers(CustomerID).

```sql
CREATE TABLE Orders(OrderID INT,OrderDate DATE NOT NULL, CustomerID INT, PRIMARY KEY(OrderID), FOREIGN KEY(CustomerID) REFERENCES Customers(CustomerID))
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
