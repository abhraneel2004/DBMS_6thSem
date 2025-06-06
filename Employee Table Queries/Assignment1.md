# Table Creation and insert Values


## Table Schema

![alt text](image.png)

## Table Data

![alt text](image-3.png)

### Create the following table using SQL query and perform insert, select and describe queries


- Create query
```sql
create table job_history(Employee_ID Number(3), Start_Date date, End_Date date, Job_ID varchar2(15), Department_ID Number(3));
```

Output

![alt text](Table_created.png)

- Insert query
```sql
 insert into job_history values ('&eid','&s_date','&e_date','&jid','&did');
```

Output

![alt text](image-1.png)

- Select query
```sql
select * from job_history;
```
Output

![alt text](image-3.png)

### Display Emp_ID, Job_Id, Department_ID for all entries

```sql
select employee_id, job_id, department_id from job_history;
```

Output

![alt text](image-4.png)

### Display the same where emp_id = 102

```sql
select employee_id, job_id, department_id from job_history where employee_id = 102;
```

Output

![alt text](image-5.png)

### Display the same where emp_id < 115

```sql
select employee_id, job_id, department_id from job_history where employee_id < 115;
```

Output

![alt text](image-6.png)

### Display the same where emp_id < 115 and department_id <100

```sql
select employee_id, job_id, department_id from job_history where employee_id < 115 and department_id < 100;
```

Output

![alt text](image-7.png)

### Display the same where emp_id < 115 or department_id <100

```sql
select employee_id, job_id, department_id from job_history where employee_id < 115 or department_id < 100;
```

Output

![alt text](image-8.png)

### For emp_id = 114 make end_date = 30-Nov-2000

```sql
update job_history set end_date='30-NOV-2000' where employee_id = 114;
```

### For department_id = 20 make start_date = 15-Feb-1995

```sql
update job_history set start_date='15-FEB-1995' where department_id = 20;
```

### Find number of days passed after he/she has left the job

```sql
select sysdate-end_date as Days_passed from job_history;
```

Output

![alt text](image-9.png)