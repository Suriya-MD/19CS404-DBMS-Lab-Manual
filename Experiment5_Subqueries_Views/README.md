# Experiment 5: Subqueries and Views
### Name: SURIYA M
### Reg No: 212223110055
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
#### SUBMISSION 


**Question 1**
--
![image](https://github.com/user-attachments/assets/89eb6b86-2a0b-4fe2-8f39-42140b508a6d)


```sql
select  o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id from orders as o
join salesman as s on o.salesman_id = s.salesman_id where s.city = 'London';
```

**Output:**

![image](https://github.com/user-attachments/assets/c4771af6-3229-4d02-9aa5-9ff97736f909)

**Question 2**
---
![image](https://github.com/user-attachments/assets/cb187f11-08f6-4815-b951-ce7166521014)

```sql
select c.ord_no, c.purch_amt, c.ord_date, c.customer_id ,c.salesman_id from orders as c
join salesman as s on c.salesman_id = s.salesman_id 
where s.city = 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/182e821f-0ac2-4b26-bb31-e7579d0c3c3a)

**Question 3**
---
![image](https://github.com/user-attachments/assets/98bef94b-fc28-462b-98de-d6173815db6d)

```sql
select department_id, department_name
from Departments
where length(department_name) > (select (avg(length(department_name))) from Departments);
```

**Output:**

![image](https://github.com/user-attachments/assets/e79cac22-1f54-4e16-9ffe-57cd8d9f28d1)

**Question 4**
---
![image](https://github.com/user-attachments/assets/a9bf8965-dc93-4cde-a49f-2ea607026a49)

```sql
select  o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
from orders as o
join salesman as s on o.salesman_id = s.salesman_id
where s.city = 'New York';
```

**Output:**

![image](https://github.com/user-attachments/assets/3a966202-e7c4-4ac3-8b0d-d07232d1ea52)

**Question 5**
---
![image](https://github.com/user-attachments/assets/6185b130-4f6d-4555-bcb4-353669d073cf)

```sql
select   student_name,  grade from GRADES g
where grade = (select max(grade) from GRADES
where subject = g.subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/5d0bfdea-285a-4390-81bc-5a20659bfabd)

**Question 6**
---
![image](https://github.com/user-attachments/assets/1a5d01b0-d967-4ab7-9370-1dbd139210c8)

```sql
select * from CUSTOMERS
where salary > 4500;
```

**Output:**

![image](https://github.com/user-attachments/assets/725e9da4-ac40-4645-9379-fb9ad4161115)

**Question 7**
---
![image](https://github.com/user-attachments/assets/6b95d6af-0cf4-4aa0-a532-5b080a81e52c)

```sql
select * from CUSTOMERS
 where age < 30;
```

**Output:**

![image](https://github.com/user-attachments/assets/35204d4a-c4de-41f3-98b3-390b380268c1)

**Question 8**
---
![image](https://github.com/user-attachments/assets/5ccf1a2d-26c9-4370-a530-cd159351d78b)

```sql
select o.ord_no, o.purch_amt, o.ord_date, o.customer_id , o.salesman_id from orders as o
join salesman as s on o.salesman_id = s.salesman_id 
where s.name = 'Paul Adam';
```

**Output:**

![image](https://github.com/user-attachments/assets/50c07723-c6b0-451e-866b-188f60be2a12)

**Question 9**
---
![image](https://github.com/user-attachments/assets/9b743d57-e208-4df3-85c0-2f495f678407)

```sql
select * from CUSTOMERS
where ADDRESS like 'DELHI' and AGE < 30
order by ID asc;
```

**Output:**

![image](https://github.com/user-attachments/assets/4c8c1126-cba3-476e-a623-86ea741de664)

**Question 10**
---
![image](https://github.com/user-attachments/assets/e89ffa0f-c440-47b3-b13a-17418eb2a626)

```sql
select * from CUSTOMERS
where ADDRESS like 'DELHI';
```

**Output:**

![image](https://github.com/user-attachments/assets/41b8531c-a394-40dc-a6fe-effc4168d504)

## Screenshot of Module 4 SEB Completion Grades
<img width="1097" height="75" alt="image" src="https://github.com/user-attachments/assets/f10e5082-96fe-4952-9aae-6e45ecd73783" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
