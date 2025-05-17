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
![image](https://github.com/user-attachments/assets/e98d1edf-7bd5-46cf-8553-fc736d869040)


```sql
SELECT InsuranceCompany,AVG(EndDate-StartDate) AS AvgCoverageDurationDays FROM Insurance GROUP BY InsuranceCompany 
```

**Output:**

![image](https://github.com/user-attachments/assets/57a71a80-5019-4b91-b42f-3f0d2f557e8f)


**Question 2**
---
![image](https://github.com/user-attachments/assets/cc022d0d-6290-42b9-b353-a46baa204649)


```sql
SELECT Diagnosis, COUNT(*) AS DiagnosisCount FROM MedicalRecords GROUP BY Diagnosis ORDER BY COUNT(*) DESC LIMIT 1
```

**Output:**

![image](https://github.com/user-attachments/assets/79a6bb3e-d29a-498a-b335-177c9b588780)


**Question 3**
---
![image](https://github.com/user-attachments/assets/8100c955-af30-4a68-876e-11eadcf43d45)


```sql
SELECT InsuranceCompany, COUNT(*) AS TotalExpiredPatients FROM Insurance GROUP BY InsuranceCompany 
```

**Output:**

![image](https://github.com/user-attachments/assets/a7af8165-b68c-44da-9bd3-82fea57a5643)


**Question 4**
---
![image](https://github.com/user-attachments/assets/3b4a6bbc-d02a-4031-b9f9-fe8a4dc141a7)


```sql
SELECT COUNT(*) AS COUNT FROM employee WHERE age>32
```

**Output:**

![image](https://github.com/user-attachments/assets/ebe1c574-2378-4e8b-99e2-ae6e99b3fec1)


**Question 5**
---
![image](https://github.com/user-attachments/assets/51dc35d5-39d8-4989-af9f-2f0bfe51f935)


```sql
SELECT SUM(workhour) AS [Total working hours] FROM employee1
```

**Output:**

![image](https://github.com/user-attachments/assets/2435374b-5b61-4eb1-95b8-01989e7ebad1)


**Question 6**
---
![image](https://github.com/user-attachments/assets/c35fbde1-ea15-4596-ad3c-fa4c6073adab)


```sql
SELECT name AS Employee_Name, MIN(age) AS Age FROM employee 
```

**Output:**

![image](https://github.com/user-attachments/assets/cdce9f23-1e34-48bd-a3c5-599099eed1c8)


**Question 7**
---
![image](https://github.com/user-attachments/assets/81efcc68-a994-4597-9bbe-ec93ae754f8f)


```sql
SELECT AVG(income) AS Average_Salary FROM employee
```

**Output:**

![image](https://github.com/user-attachments/assets/ba2bd2a8-b40b-4e80-a416-b2a9931de2a1)


**Question 8**
---
![image](https://github.com/user-attachments/assets/3bff0102-84c4-40d7-a1ac-c440d104a9ca)


```sql
SELECT (age/5)*5 AS age_group,MIN(age) FROM customer1 GROUP BY (age/5)*5 HAVING (age/5)*5<25
```

**Output:**

![image](https://github.com/user-attachments/assets/c5bf1836-0a09-4072-9535-0881cf30def2)


**Question 9**
---
![image](https://github.com/user-attachments/assets/3f54c189-69b4-4289-a7a1-7522edaf9152)


```sql
SELECT address,SUM(salary) FROM customer1 GROUP BY address HAVING SUM(salary)>2000
```

**Output:**

![image](https://github.com/user-attachments/assets/68d51df6-4032-431d-a0ca-8e4d46372762)


**Question 10**
---
![image](https://github.com/user-attachments/assets/f990ca17-19bb-4023-a6a2-117d35afa01c)


```sql
SELECT category_id,AVG(Price) FROM products GROUP BY category_id HAVING AVG(price) BETWEEN 10 AND 15
```

**Output:**

![image](https://github.com/user-attachments/assets/99ffeec7-bc1e-4a4e-b059-de284abb7d5f)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
