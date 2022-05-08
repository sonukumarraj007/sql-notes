### Stored Procedure
#### A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.


```sql
create PROCEDURE `get_student_info`()
BEGIN
select * from student;
END
```

```sql
call get_student_info;
```


#### In Parameter

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_student_info_by_age`(in age int)
BEGIN
select * from student where student.age = age;
END
```

```sql
call get_student_info_by_age(28);

call college.get_student_info_by_age(28);
```

#### Out keyword

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_student_info_count`(out records int)
BEGIN
select count(*) into records from student where student.age = 28;
END
```

```sql
call college.get_student_info_count(@record);
select @record as total_records;
```


#### Inout

```sql
CREATE DEFINER=`root`@`localhost` PROCEDURE `get_student_info_count_by_age`(inout records int, in age int)
BEGIN
select count(*) into records from student where student.age = age;
END
```

```sql
call college.get_student_info_count_by_age(@record, 28);
select @record as total_records;
```