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
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/dffade3a-1cbf-4ba3-9612-196ffd3f0a7d)
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
 UPDATE manager SET Salary = Salary + (Salary * 10/100);
```
### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/631584f9-cb67-49a1-ab5b-2eaea2a346fc)
```


### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```
 delete from manager where salary<2750;
```
### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/64f70250-a642-4c1a-8d86-90ba71a67625)
```


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```
 alter table manager rename column ename to name;
 alter table manager rename column annualsalary to Annual_salary;
```
### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/f730c697-bb01-4c29-b233-19efb549697e)
```

### Q5)	List the names of Clerks from emp table.

### QUERY:
```
select name from manager where designation='clerk';
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/9d152e5e-8c38-42f5-9d55-58b9e6dbd989)
```

### Q6)	List the names of employee who are not Managers.

### QUERY:
```
 select name from manager where designation !='manager';
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/91647373-c991-461d-bb69-9f10f1c95bbb)
```

### Q7)	List the names of employees not eligible for commission.

### QUERY:
```
 select name from manager where commission=0;
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/323177a4-e00a-4b98-8e44-a2ed6be71905)
```

### Q8)	List employees whose name either start or end with ‘s’.

### QUERY:
```
 SELECT * FROM manager WHERE name LIKE '%S' AND name like 'S%';
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/77b49ea1-99ff-482f-b7a4-9939409ef0be)
```

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```
 select * from manager order by Hiredate,name, designation,deptno asc;
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/0b43b938-04e7-4f97-8fbd-d489a72a5c51)
```

### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where Hiredate<1981-09-30;
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/9c8af117-9fbf-41eb-9eac-783ebabe2967)
```

### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select name, deptno ,salary from manager order by deptno asc;
select name, deptno ,salary from manager order by salary desc;
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/4c10df17-584a-4707-9e47-02bc3cd4ab23)
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/f174ec56-71fd-4821-87d8-95e652a448af)
```

### Q12) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```
 select name from manager where deptno != 10;
 select name from manager where deptno != 30;
 select name from manager where deptno != 40;
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/16a17b68-7443-478d-8bc4-33a7ca9fc2eb)
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/7ea3f5be-2619-4ef0-854a-eca5b3696a1c)
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/8dd1b06e-4393-4b92-a0a1-393bcc16d900)

```

### Q13) Find number of rows in the table EMP

### QUERY:
```
 select count(*) as no_rows from manager;
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/87e694da-1e57-45e9-8b67-f1e5070332fb)
```

### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select min(Annual_salary) as Minimum from manager;
select max(Annual_salary) as Maximum from manager;
select avg(Annual_salary) as Average from manager;
```

### OUTPUT:
```
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/84b79cf0-4c70-47c1-a365-b897636ca1e0)
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/59200bee-eb07-4b3d-93bc-2fc760771e29)
![image](https://github.com/Meetha22003992/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119401038/0c7cdfe1-a1d5-439d-9404-85f4c926443a)
```

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:


### OUTPUT:
