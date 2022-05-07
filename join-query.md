### SQL Join

#### Inner Join
#### Left Join
#### Right Join
#### Full Join
#### Natural Join
#### Cross Join


```sql
show databases;
```

```sql
create database college;
```

```sql
use college;
```


```sql
create table student(
student_id int auto_increment,
first_name varchar(25) not null,
last_name varchar(25) not null,
age int,
primary key(student_id)
);
```


```sql
insert into student values 
(1, 'sonu', 'kumar',28),
(2, 'rahul', 'jha',26),
(3, 'vikash', 'kumar',24),
(4, 'atul', 'jha',28),
(5, 'sandeep', 'kumar',23),
(6, 'anshu', 'kumar',28);
```

```sql
select * from student;
```

```sql
create table department(
student_id int auto_increment,
department_name varchar(25) not null,
foreign key(student_id) references student(student_id)
);
```

```sql
insert into department values 
(1, 'cse'),
(2, 'me'),
(3, 'civil'),
(4, 'cse');
```

```sql
select * from department;
```

# Inner Join 
####  whichever data are common on both table that will come

```sql
select student.first_name, student.last_name, student.age, department.department_name
from student 
inner join department 
on student.student_id = department.student_id;
```

# Left Join
#### all data from left side table

```sql
select student.first_name, student.last_name, student.age, department.department_name
from student 
left join department 
on student.student_id = department.student_id;
```

# Right Join
#### all data from right side table

```sql
select student.first_name, student.last_name, student.age, department.department_name
from student 
right join department 
on student.student_id = department.student_id;
```


/* Full Join */
```sql
select student.first_name, student.last_name, student.age, department.department_name
from student 
left join department 
on student.student_id = department.student_id
union
select student.first_name, student.last_name, student.age, department.department_name
from student 
right join department 
on student.student_id = department.student_id;
```

### Cross Join
#### all the possible combination
```sql
select student.first_name, student.last_name, student.age, department.department_name
from student 
cross join department;
```

### Natural Join
```sql
select student.first_name, student.last_name, student.age, department.department_name
from student 
natural join department;
```










