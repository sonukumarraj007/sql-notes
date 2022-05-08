# Basic Query

``# Single line comment``
``/* Multi line comment */``

### create database

```sql
create database customers;
```

### drop exting database

```sql
drop database customers;
```

### to get list of databases

```sql
show databases;
```

### before writing any query select database

```sql
use customers;
```

### to get list of table in selected database

```sql
show tables;
```

### create table in database

```sql
create table customer_info(
id integer auto_increment,
first_name varchar(10),
last_name varchar(10),
salary integer,
primary key(id)
);
```

### drop table

```sql
drop table customer_info;
```

### shows structure of table

```sql
desc customer_info;
```

### insert single row data

```sql
insert into customer_info(first_name, last_name, salary) values ("Sonu", "Kumar", 1000);
```

### insert multiple row data

```sql
insert into customer_info(id, first_name, last_name) 
values ("Vikash", "K", 3000), ("Rahul", "J", 2000);
```

### get all data from table

```sql
select * from customer_info;
```

### insert null value

```sql
insert into customer_info(first_name, last_name, salary) values ("DK",null,null);
```

### is null show only null data in selected column

```sql
select * from customer_info where salary is null;
```

### is not null show only not null data in selected column

```sql
select * from customer_info where first_name is not null;
```

### update 

```sql
update customer_info set salary = 5000 where id=1;
```

### delete 

```sql
delete from customer_info where id=2;
```


### alter query
### add new column in exting table

```sql
alter table customer_info add dob date;
```

### modify column in exting table

```sql
alter table customer_info modify dob year;
```

### droping column from table

```sql
alter table customer_info drop column dob;
```














