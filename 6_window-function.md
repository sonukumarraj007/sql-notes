### Window function

#### a window function or analytic function is a function which uses values from one or multiple rows to return a value for each row. 

#### Window functions have an OVER clause; any function without an OVER clause is not a window function, but rather an aggregate or single-row function.

### Types of Window functions :
#### Analytical
#### Aggregate


#### Aggregate functions : An aggregate function computes the aggregate values of a particular row and returns the value. For example : sum() returns sum of a row. This returns a single result.

#### They are : sum, avg, min, max etc. This is same as we studied in python and in school.

#### Analytical functions : An analytic function computes values over a group of rows and returns a single result for each row. This is different from an aggregate function, which returns a single result for an entire group of rows.

#### They are : Cumulative distribution, row number, dense rank, rank, ntile, lag, lead, firstvalue, last value etc. We will see each one with a example and we will get more understanding.

- ROW_NUMBER
- RANK
- DENSE_RANK
- LAG
- LEAD


```sql
select dept_name, max(salary) as max_salary
from employee
group by dept_name;
```


```sql
select e.*,
    max(salary) over(partition by dept_name) as max_salary
from employee e;
```

### ROW_NUMBER


```sql
select e.*,
    row_number() over() as rn
from employee e; 
```


```sql
select e.*,
    row_number() over(partition by dept_name ) as rn
from employee e; 
```

#### fetch the first 2 employees from each department to join the company first.


```sql
select * from (
    select e.*,
    row_number() over(partition by dept_name order by emp_id) as rn
    from employee e) emp
where emp.rn < 3;
```

### RANK
##### rank will skip row value for every duplicate that found previously

#### fetch the top 3 employees in each department earning the max salary


```sql
select * from (
    select e.*,
    rank() over(partition by dept_name order by salary desc) as rnk
    from employee e
) emp
where x.rnk < 4;
```

### DENSE_RANK

#### dense_rank will not skip value


```sql
select e.*,
    dense_rank() over(partition by dept_name order by salary desc) as dense_rnk
from employee e;
```


```sql
select e.*,
    rank() over(partition by dept_name order by salary desc) as rnk,
    dense_rank() over(partition by dept_name order by salary desc) as dense_rnk
from employee e;
```

### LAG

#### fetch a query to display if the salary of an employee is higher, lower or
#### equal to the previous employee


```sql
select e.*,
    lag(salary) over (partition by dept_name order by emp_id) as prev_emp_salary
from employee e;
```

### LEAD

#### lead(salary, 2, 0)


```sql
select e.*,
    lead(salary) over (partition by dept_name order by emp_id) as next_emp_salary
from employee e;
```


```sql
select e.*,
lead(salary) over (partition by dept_name order by emp_id) as prev_emp_salary
case  
    when e.salary >lag(salary) over(partition by dept_name order by emp_id) then 'Higher than previous employee'
    when e.salary < lag(salary) over(partition by dept_name order by emp_id) then 'Lower than previous employee'
    when e.salary = lag(salary) over(partition by dept_name order by emp_id) then 'Same as than previous employee'
end sal_range
from employee;
```