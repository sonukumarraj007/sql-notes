### Basic Select Query.

```sql
show databases;
```


```sql
use hr_db;
```


```sql
show tables;
```


```sql
desc employees;
```


```sql
select * from employees;
```


```sql
select * from employees where salary > 10000;
```


```sql
select  COUNT(*) from employees;
```


```sql
select COUNT(country_name) from countries;
```


```sql
select DISTINCT manager_id from employees;
```


```sql
select DISTINCT manager_id from employees where manager_id > 105;
```


```sql
select * from employees limit 5;
```


```sql
select * from employees where department_id = 6 LIMIT 5;
```


```sql
select * from employees where first_name like 'A%';
```


```sql
select * from employees where first_name like '%M';
```


```sql
select * from employees where employee_id >= 200 AND salary <= 50000;
```


```sql
select * from employees where salary between 5000 AND 8000;
```


```sql
select  * from employees where job_id = 9 OR job_id = 5;
```


```sql
select  * from employees where job_id IN(9,6,11);
```


```sql
select * from employees order by first_name;
```


```sql
select * from employees order by salary;
```

```sql
select * from employees order by salary desc;
```


```sql
select * from employees order by 3;
```


```sql
select COUNT(department_id) from employees group by department_id;
```


```sql
select COUNT(department_id) as dep_count from employees group by department_id;
```


```sql
select COUNT(department_id) as dep_count from employees group by department_id having COUNT(department_id) > 4;
```


```sql
select SUM(salary) from employees;
```


```sql
select MIN(salary) from employees;
```


```sql
select MAX(salary) from employees;
```


```sql
select AVG(salary) from employees;
```


```sql
select ROUND(salary) from employees;
```


```sql
select LENGTH(first_name) from employees;
```


```sql
select UCASE(first_name) from employees;
```


```sql
select LCASE(first_name) from employees;
```


```sql
select * from employees where  LCASE(first_name) = 'john';
```


```sql
select DAY(hire_date) from employees where department_id = 6;
```


```sql
select MONTH(hire_date) from employees where department_id = 6;
```


```sql
select YEAR(hire_date) from employees where department_id = 6;
```


```sql
select * from employees where salary > (select AVG(salary) from employees);
```


```sql
select first_name, last_name from employees where salary > (select AVG(salary) from employees);
```


```sql
select distinct city from employees where city REGEXP '^[AEIOU]';
```


```sql
select distinct city from employees where NOT city REGEXP '^[AEIOU]';
```

