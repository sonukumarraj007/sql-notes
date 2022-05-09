### Sub-query

A subquery is a query that appears inside another query statement.

Outer query / Main query, subquery/Inner quert

#### Different types of sub-query

- scalar
- multiple
- correlated


### scalar

It always retuns 1 row and 1 column

#### find the employees who's salary is more than the average salary earned by all employee

```sql
select * 
from employee
where salary > ( select avg(salary) from employee);
```


### Multiple row sub-query

1. Sub-query which retuns multiple column and multiple row

2. Sub-query which return only 1 column and multiple row

####  multiple column and multiple row

#### find the employees who earn the highest salary in each department

```sql
select * 
from employee
where (dept_name, salary) in ( select dept_name, max(salary)
                                from employee
                                group by dept_name
                              );
```


#### Single column multiple row

#### find department who do not have any employees

```sql
select *
from department
where dept_name not in ( select distinct dept_name from employee);
```


### Correlated sub-query

A sub-query which is related to the outer query.

#### find the employees in each department who earn more than the average salary in the department


```sql
select * 
from employee e1
where salary > ( select avg(salary) 
                 from employee e2
                 where e2.dept_name = e1.dept_name );
```

#### find department who do not have any employee


```sql
select * 
from department d
where not exists ( select 1 from employee e
                    where e.dept_name = d.dept_name );
```

#### Nested sub-query

sub-query inside a subquery.


#### find stores who's sales better than the average sales accross all stores


```sql
select * 
from ( select store_name, sum(price) as total_sales 
        from sales
        group by store_name ) sales
join ( select avg(total_sales) as sales
        from ( select store_name, sum(price) as total_sales
                from sales
                group by store_name) x ) avg_sales
on sales.total_sales > avg_sales.sales ;
```
