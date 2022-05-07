show databases;

use hr_db;

show tables;

desc employees;

select * from employees;

select * from employees where salary > 10000;

select  COUNT(*) from employees;

select COUNT(country_name) from countries;

select DISTINCT manager_id from employees;

select DISTINCT manager_id from employees where manager_id > 105;

select * from employees limit 5;

select * from employees where department_id = 6 LIMIT 5;

select * from employees where first_name like 'A%';

select * from employees where first_name like '%M';

select * from employees where employee_id >= 200 AND salary <= 50000;

select * from employees where salary between 5000 AND 8000;

select  * from employees where job_id = 9 OR job_id = 5;

select  * from employees where job_id IN(9,6,11);

select * from employees order by first_name;

select * from employees order by salary;

select * from employees order by salary desc;

select * from employees order by 3;

select COUNT(department_id) from employees group by department_id;

select COUNT(department_id) as dep_count from employees group by department_id;

select COUNT(department_id) as dep_count from employees group by department_id having COUNT(department_id) > 4;

select SUM(salary) from employees;

select MIN(salary) from employees;

select MAX(salary) from employees;

select AVG(salary) from employees;

select ROUND(salary) from employees;

select LENGTH(first_name) from employees;

select UCASE(first_name) from employees;

select LCASE(first_name) from employees;

select * from employees where  LCASE(first_name) = 'john';

select DAY(hire_date) from employees where department_id = 6;

select MONTH(hire_date) from employees where department_id = 6;

select YEAR(hire_date) from employees where department_id = 6;

select * from employees where salary > (select AVG(salary) from employees);

select first_name, last_name from employees where salary > (select AVG(salary) from employees);

select distinct city from employees where city REGEXP '^[AEIOU]';

select distinct city from employees where NOT city REGEXP '^[AEIOU]';
