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
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/91256993-585e-45d0-85cd-48a02ebe599e)


### Q2) Delete the records from manager table where the salary less than 2750.
### QUERY:
```
delete from manager where salary<2750;
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/8ff45c41-69b9-4302-8d96-b13a951de817)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```
### OUTPUT:

![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/e8a905f4-a5d3-4a89-b992-4eee1ec3ab0c)

### Q4) List the names of Clerks from emp table.
### QUERY:
```
select ename from manager where designation='clerk';
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/5e73e99b-a275-48a9-9d89-67322635c070)

### Q5)	List the names of employee who are not Managers.
### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/3bb8a9f3-5d98-41bd-89a1-388f7e3b9e55)

### Q6)	List the names of employees not eligible for commission.
### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/4104f6b4-04f5-4081-9b10-2571aed555eb)

### Q7)	List employees whose name either start or end with ‘s’
### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/e8209d84-e8d5-4563-8731-62f0534cd778)

### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/0e99d8e5-d015-40c2-864f-a484146bbd86)

### Q9) List the Details of Employees who have joined before 30 Sept 81.
### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/7833ba32-35bb-4244-a619-887819f126e9)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/1f7884fc-25e5-4e67-950b-aade1847d5f8)

### Q11) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/3c5b26e5-7aa5-4550-b4d3-f490f4f451c0)

### Q12) Find number of rows in the table EMP
### QUERY:
```
select count(*) from manager;
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/70d90a43-2fa2-41cb-9262-fb1fb4a0d85f)

### Q13) Find maximum, minimum and average salary in EMP table.
### QUERY:
## MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/caaf3098-dab4-4db8-996b-019c92693ffa)

## MINIMUM:
```
select min(salary) from manager;
```
## OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/e363922b-b1dc-4fea-b4d4-c28ae7914603)

## AVERAGE:
```
select avg(salary) from manager;
```
## OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/063778b4-3e0b-4b6e-b71f-370bb78f3a15)

### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```
### OUTPUT:
![image](https://github.com/kavinesh8476/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118466561/59ce3e6a-611c-4c33-853d-fa75b94913ef)

### Name :Kavinesh M
### Register no:212222230064
### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
