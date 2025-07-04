# Customer Table Queries

### Table Creation

```sql
create table my_customers(cutomer_id Number(3), cust_first_name varchar2(15), cust_last_name varchar2(15), Territory varchar2(10), credit_limit Number(6,2), Mgr_id Number(3), DOB date, Marital_Status Varchar(10), Gender varchar2(1), Income_level varchar2(20));

insert into my_customers values('&cid','&cfn','&cln', '&terr', '&crl', '&mid', '&dob','&ms','&gen', '&inc');
```

### Table Schema

```sql
desc my_customers;
```

Output

![alt text](image.png)

## Table Data

![alt text](image-3.png)

### Create table of any name but schema must be same as my customers

```sql
create table c as select * from my_cutomers where 1=2;

desc c;
```

Output

![alt text](image.png)

### Rename the table to Customers_2011

```sql
alter table c rename to customers_2011;
```

![alt text](Table_altered.png)


### Show all tables in your system

```sql
select * from tab;
```

### Change datatype of income_level from varchar2(20) to Number(8,2)

```sql
ALTER TABLE customers_2011 MODIFY income_level NUMBER(8,2);
```

![alt text](Table_altered.png)

```sql
desc customers_2011;
```

Output

![alt text](image-1.png)

### Change the attribute name income_level to income

```sql
alter table customers_2011 rename column income_level to income;

desc customers_2011;
```

![alt text](image-2.png)

### Show each customer's Id and along with their Manager name

```sql
select c1.cust_first_name || ' ' || c1.cust_last_name as Customer_Name, c2.cust_first_name || ' ' || c2.cust_last_name as Manager_Name from customers_2011 c1, customers_2011 c2 where c1.mgr_id = c2.customer_id;
``` 

Output

![alt text](image-4.png)

### Show each customer's Id and along with their Manager ID

```sql
select customer_id, mgr_id from customers_2011;
``` 

Output

![alt text](image-5.png)

### Add attribute city varchar2(25) and set value to this for each customer

```sql
alter table customers_2011 add city varchar2(25);

update customers_2011 set city='&city' where customer_id='&cid';
```

Output


