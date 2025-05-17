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
![image](https://github.com/user-attachments/assets/a0cf9ad9-1983-40b3-8c34-cc8ba2472a19)


```sql
SELECT grade,COUNT(*) FROM customer GROUP BY grade HAVING grade>(SELECT AVG(grade) FROM customer WHERE city='New York')
```

**Output:**

![image](https://github.com/user-attachments/assets/0d46e74f-7acd-4ec8-b19b-81162e04c697)


**Question 2**
---
![image](https://github.com/user-attachments/assets/7b2f6327-c5dc-4bfb-a41e-6045c89af227)

```sql
SELECT * FROM orders WHERE salesman_id IN(SELECT salesman_id FROM salesman WHERE city='New York')
```

**Output:**

![image](https://github.com/user-attachments/assets/b9ff3920-f158-44ff-9b72-87aa9e3d777f)

**Question 3**
---
![image](https://github.com/user-attachments/assets/651fe49a-fbf9-4253-af90-b1d27af3632c)

```sql
SELECT commission FROM salesman WHERE salesman_id IN (SELECT salesman_id FROM customer WHERE city='Paris')
```

**Output:**

![image](https://github.com/user-attachments/assets/8b333c16-dc35-4067-b754-6d122fc76407)


**Question 4**
---
![image](https://github.com/user-attachments/assets/51fd89e7-edcf-4adc-a750-4637a6d3f5bb)


```sql
SELECT *
FROM Grades g
WHERE grade = (
    SELECT MIN(grade)
    FROM Grades
    WHERE subject = g.subject
);
```

**Output:**

![image](https://github.com/user-attachments/assets/09d71013-a17f-4885-9a3c-02b09d6719b1)


**Question 5**
---
![image](https://github.com/user-attachments/assets/542d91d6-9a87-467c-aeda-12b940e2ca67)


```sql
SELECT student_name, grade
FROM Grades g
WHERE grade = (
    SELECT MIN(grade)
    FROM Grades
    WHERE subject = g.subject
);

```

**Output:**

![image](https://github.com/user-attachments/assets/aadd328e-5b3e-407d-8e84-d2775cdbedb8)


**Question 6**
---
![image](https://github.com/user-attachments/assets/1b23833a-fabb-48a9-aeb9-241d54a7aef2)


```sql
SELECT * FROM orders WHERE salesman_id=(SELECT salesman_id FROM salesman WHERE name='Paul Adam')
```

**Output:**

![image](https://github.com/user-attachments/assets/ef29f18a-6b70-4c36-9b53-fbbb16743a36)


**Question 7**
---
![image](https://github.com/user-attachments/assets/c5f6ef0d-29f4-458c-9d01-e246af5fbf9f)


```sql
SELECT name FROM customer WHERE phone IN (SELECT phone FROM customer GROUP BY phone HAVING COUNT(phone)=1)
```

**Output:**

![image](https://github.com/user-attachments/assets/47a78f64-3051-4ec2-9313-50c08d65c0ee)


**Question 8**
---
![image](https://github.com/user-attachments/assets/46da8f0c-130d-4e69-b2c4-054db522988b)


```sql
SELECT * FROM Employee WHERE age<(SELECT AVG(age) FROM Employee WHERE income>250000)
```

**Output:**

![image](https://github.com/user-attachments/assets/b7921748-3f2b-4489-8d94-25555ed91640)


**Question 9**
---
![image](https://github.com/user-attachments/assets/744e1244-245b-4ed7-9845-fb9cecdd4ec9)


```sql
SELECT * FROM CUSTOMERS WHERE SALARY=1500
```

**Output:**

![image](https://github.com/user-attachments/assets/1574b949-2f3e-4df6-8112-dffd70be6a33)


**Question 10**
---
![image](https://github.com/user-attachments/assets/e116a2a9-9740-4dd6-a22e-66b15b24fe92)


```sql
SELECT * FROM customer WHERE city!=(SELECT city FROM customer WHERE id=(SELECT max(id) FROM customer))
```

**Output:**

![image](https://github.com/user-attachments/assets/a98fabb1-8347-43dc-9831-24da5cf12ba8)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
