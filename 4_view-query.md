### Views Query

##### A VIEW is a virtual table, which is a result of a query.
##### They can be used to create virtual tables of complex queries.
##### update, agreegate function, sub-query, having, groupby, union, left join, right join, will not work in view 

```sql
create view student_info as 
select first_name, last_name, age from student
inner join department using(student_id);
```


```sql
select * from student_info;
```


```sql
drop view student_info;
```