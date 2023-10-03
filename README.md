# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/4738a852-02cd-4151-8be2-588950155f29)


### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/d2be0414-24ee-4b80-adff-9f460eecf4b3)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/df530ca0-5799-4f6c-88d3-db510541c2ce)

### Q4) List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/11a90688-1500-4c78-8615-4b61e24450ac)

### Q5)	List the names of employee who are not Managers.
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/f9c1460c-fa6d-41b7-acf2-1c5ef18b2d87)

### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/ab677878-c633-43ff-a7eb-9a85d6a38658)

### Q7)	List employees whose name either start or end with ‘s’
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/1383f0ea-fde9-484d-8fd5-cf17b5f175aa)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/dca8955f-6d28-4cef-9d7a-1eefe6552a1d)

### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/a45671c2-0bee-453b-9771-c4aaf650aa38)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/190fda6c-1b0b-4cbe-ba49-4fb54ce029eb)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/69c77793-fa68-45f5-aa14-3f9eac85eb37)

### Q12) Find number of rows in the table EMP
### QUERY:
```
select count(*) from manager;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/0eba97ad-bb9a-4271-a554-6b8aa3354b4f)

### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
## MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/ff11d145-eed4-4868-8d15-17366062963b)

## MINIMUM:
```
select min(salary) from manager;
```
## OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/67bf19f6-05e7-400d-aa94-c01ba7c9835d)

## AVERAGE:
```
select avg(salary) from manager;
```
## OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/99409376-57f9-4b29-8e85-6eec868ff205)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![image](https://github.com/BharathCSEIOT/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/122793480/e16c9bf7-c965-4e1b-aa78-cd0481c32024)

### Name :Kavinesh M
### Register no:212222230064
### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
