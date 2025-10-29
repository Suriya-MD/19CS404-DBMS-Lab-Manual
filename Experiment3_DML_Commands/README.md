# Experiment 3: DML Commands
### Name: SURIYA M
### Reg No: 212223110055
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
<img width="1029" height="449" alt="image" src="https://github.com/user-attachments/assets/b2f63fca-ab6d-459c-8373-b189894f9390" />

```sql
UPDATE sales
SET total_sell_price = quantity * sell_price
WHERE product_id = 10;
```

**Output:**

<img width="968" height="238" alt="image" src="https://github.com/user-attachments/assets/2db88ec8-546a-4b0c-82c0-72c5b256f5f7" />

**Question 2**
---
<img width="1182" height="519" alt="image" src="https://github.com/user-attachments/assets/0780bc6d-fdea-441d-84c2-3533b01ee8b4" />

```sql
UPDATE products
SET reorder_lvl = reorder_lvl * 0.7
WHERE LOWER(product_name) LIKE '%cream%'
  AND quantity > reorder_lvl;
```

**Output:**

<img width="1239" height="286" alt="image" src="https://github.com/user-attachments/assets/6df5670e-e6bc-4d9a-b0ce-cbaf85037209" />

**Question 3**
---
<img width="1198" height="620" alt="image" src="https://github.com/user-attachments/assets/1dd1333f-87ad-4728-8106-745945d09f31" />

```sql
UPDATE purchases
SET per_unit_price = 25,
    total_price = quantity * 25
WHERE purchase_date = '2022-08-15'
  AND product_id = 12;
```

**Output:**

<img width="1168" height="297" alt="image" src="https://github.com/user-attachments/assets/f474d0f3-1e8e-4c1e-814f-f8b16377cf37" />

**Question 4**
---
<img width="1146" height="463" alt="image" src="https://github.com/user-attachments/assets/a5367b38-d1cb-432c-97d5-92390657d6b0" />

```sql
UPDATE employees
SET salary = CASE
    WHEN department_id = 40 THEN ROUND(salary * 1.25)
    WHEN department_id = 90 THEN ROUND(salary * 1.15)
    WHEN department_id = 110 THEN ROUND(salary * 1.10)
    ELSE salary
END;
```

**Output:**

<img width="1125" height="302" alt="image" src="https://github.com/user-attachments/assets/1d1e3548-e9bd-4c61-b417-bc210da8231a" />

**Question 5**
---
<img width="973" height="542" alt="image" src="https://github.com/user-attachments/assets/1a0b887c-daa4-49e7-bf05-1902940687d7" />

```sql
UPDATE products
SET reorder_lvl = 40
WHERE category = 'Grocery';
```

**Output:**

<img width="1713" height="274" alt="image" src="https://github.com/user-attachments/assets/53a5dfe5-7db2-43ad-82bc-74a96b40426c" />

**Question 6**
---
<img width="938" height="140" alt="image" src="https://github.com/user-attachments/assets/56ff0a45-7415-457b-8644-c5369c994cde" />

```sql
DELETE FROM doctors
WHERE specialization = 'Cardiology';
```

**Output:**

<img width="1381" height="343" alt="image" src="https://github.com/user-attachments/assets/dce28707-9de9-4689-832d-f89689f55b49" />

**Question 7**
---
<img width="1104" height="610" alt="image" src="https://github.com/user-attachments/assets/35115f53-f7ff-4567-b37b-8d551ba0921f" />

```sql
DELETE FROM doctors
WHERE specialization IS NULL;
```

**Output:**

<img width="1263" height="839" alt="image" src="https://github.com/user-attachments/assets/0d1848e8-ac23-459f-8e2a-68a7b972d0a1" />

**Question 8**
---
<img width="1252" height="682" alt="image" src="https://github.com/user-attachments/assets/23ea11a3-c844-4fd2-93ef-8677e66fe449" />

```sql
SELECT order_no, order_date, purch_amt
FROM orders
WHERE salesman_id = 5001;
```

**Output:**

<img width="1447" height="515" alt="image" src="https://github.com/user-attachments/assets/261161de-a58a-47f9-a863-55e14fba589e" />

**Question 9**
---
<img width="1198" height="611" alt="image" src="https://github.com/user-attachments/assets/7bd706b8-f769-4277-958b-b89e7cd2d1e2" />

```sql
SELECT patient_id, first_name, admission_date
FROM patients
WHERE strftime('%Y', admission_date) = '2023';
```

**Output:**

<img width="1094" height="357" alt="image" src="https://github.com/user-attachments/assets/38b5e73d-d414-409d-9500-5d70cf6f59ae" />

**Question 10**
---
Write a SQL query to find customers who are either from the city 'New York' or who do not have a grade greater than 100. Return customer_id, cust_name, city, grade, and salesman_id.
<img width="534" height="285" alt="image" src="https://github.com/user-attachments/assets/47058245-733a-4239-af96-2f6e5eeeb4eb" />



```sql
SELECT customer_id, cust_name, city, grade, salesman_id
FROM customer
WHERE city = 'New York'
   OR grade <= 100
   OR grade IS NULL;
```

**Output:**

<img width="1581" height="459" alt="image" src="https://github.com/user-attachments/assets/4e16aacb-5af7-4b97-be2e-6bd31312a941" />

## Screenshot of Module 2 SEB Completion Grades
<img width="1098" height="77" alt="image" src="https://github.com/user-attachments/assets/7289986e-1920-42d9-b189-09cfbd0b142b" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
