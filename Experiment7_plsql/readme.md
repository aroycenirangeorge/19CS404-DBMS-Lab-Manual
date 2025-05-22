# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Program:**
```sql
DECLARE
    a NUMBER := 80;
    b NUMBER := 60;
BEGIN
    IF a > b THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || a);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || b);
    END IF;
END;
```

**Expected Output:**  
Greater number is: 80

**Output:**  
![image](https://github.com/user-attachments/assets/6efc0581-4fe7-4cc3-b129-015676e5a4a8)
---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Program:**
```sql
DECLARE
    n NUMBER := 10;
    i NUMBER := 1;
    sum NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
```

**Expected Output:**  
Sum of first 10 natural numbers is: 55

**Output:**  
![image](https://github.com/user-attachments/assets/c5b84f09-6d43-47f8-baf2-630ab055db47)
---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Program:**
```sql
DECLARE
    n NUMBER := 7;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER := 3;
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence: ');
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);
    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;

```

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

**Output:**  
![image](https://github.com/user-attachments/assets/25efe03b-1bf3-45a3-a948-3723407c24cd)
---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Program:**
```sql
DECLARE
    n NUMBER := 1535;
    rev NUMBER := 0;
    digit NUMBER;
    temp NUMBER;
BEGIN
    temp := n;
    WHILE temp > 0 LOOP
        digit := MOD(temp, 10);
        rev := rev * 10 + digit;
        temp := TRUNC(temp / 10);
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Original number: ' || n);
    DBMS_OUTPUT.PUT_LINE('Reversed number is: ' || rev);
END;

```

**Expected Output:**  
n = 1535  
Reversed number is 5351

**Output:**  
![image](https://github.com/user-attachments/assets/07ff547b-ec12-40c2-b50a-865bfd79f8d3)
---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Program:**
```sql
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
BEGIN
    IF (a > b) AND (a > c) THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three numbers is: ' || a);
    ELSIF (b > c) THEN
        DBMS_OUTPUT.PUT_LINE('Largest of three numbers is: ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Largest of three numbers is: ' || c);
    END IF;
END;
```

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

**Output:**  
![image](https://github.com/user-attachments/assets/ab2fa4b3-24fb-4fbe-966e-8ec37266249b)

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
