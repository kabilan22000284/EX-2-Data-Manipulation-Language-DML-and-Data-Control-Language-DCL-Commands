# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## DATE:11/8/23
## AIM:

To create a manager database and execute DML queries using SQL.

## DML(Data Manipulation Language)

The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands:

INSERT: It is used to insert data into a table.

UPDATE: It is used to update existing data within a table.

DELETE: It is used to delete records from a database table.

### Create the table as given below:
```
create table manager(enumber number(6),ename char(15),
salary number(5),commission number(4),
annualsalary number(7),Hiredate date,designation char(10),
deptno number(2),reporting char(10));
```
### insert the following values into the table
```
insert into manager values(7369,'Aarik',2500,500,30000,
'30-June-81','clerk',10,'John');
insert into manager values(7839,'Riyaz',3000,400,36000,
'1-Jul-82','manager',null,'Khan');
insert into manager values(7934,'Zayn',3500,300,42000,
'1-May-82','manager',30,NULL);
insert into manager values(7788,'Sam',4000,0,48000,
'12-Aug-82','clerk',50,'Joel');
```
### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
UPDATE manager
SET salary = salary + (salary * 0.10),
annualsalary = annualsalary + (annualsalary * 0.10);

```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/084a35be-9ba2-4eef-96a2-5fefa6874141)


### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```
DELETE FROM manager WHERE salary < 2750;

```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/dd5b8efe-58c9-49d1-a66f-b4d41baeb2f8)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```
SELECT ename AS "Name", salary * 12 AS "Annual Salary"
FROM manager;
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/ee0a0cad-9116-4103-a6e3-4db0ba1d63b1)


### Q5) List the names of Clerks from emp table.
### QUERY:
```
SELECT ename from manager where designation='clerk';
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/d087493c-6dee-40b1-8ed5-7dfddfc0481c)


### Q6) List the names of employee who are not Managers.

### QUERY:
```
SELECT ename from manager where designation!='manager';
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/181b9c3a-6dbb-4883-87ea-99ccdf696d9d)


### Q7) List the names of employees not eligible for commission.

### QUERY:
```
SELECT ename from manager where commission=0;
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/1bc3315a-538f-4252-a6ff-7641c9ce7b4d)


### Q8) List employees whose name either start or end with ‘s’.
### QUERY:
```
SELECT ename
FROM manager
WHERE ename LIKE 'S%' OR ename LIKE '%s';
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/427fa36d-1cc4-490a-82fe-b89996fec2b3)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```
select ename,designation,deptno,Hiredate from manager
order by Hiredate asc;
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/615fce5d-75ec-49c7-826d-beb6c0584012)


### Q10) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
```
SELECT *
FROM manager
WHERE Hiredate < TO_DATE('1981-09-30', 'YYYY-MM-DD');
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/e099f45e-e40d-4d0a-8b3f-8a913eae7108)


### Q11) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
```
select ename,deptno,salary from manager order by deptno asc;
select ename,deptno,salary from manager order by salary desc;
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/4709b76b-7531-4bda-8bd7-b8f8bee6e472)


### Q12) List the names of employees not belonging to dept no 30,40 & 10
### QUERY:
```
select ename from manager where deptno not in (10,30,40);
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/7aaeb946-f4cf-49fc-b378-b0b969c282c5)


### Q13) Find number of rows in the table EMP
### QUERY:
```
select count(*) from manager;
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/dcde4480-5ffe-40a3-8926-71ef3edb87ce)


### Q14) Find maximum, minimum and average salary in EMP table.
### QUERY:
```
select ename ,salary,annualsalary from manager
where salary = (select max(salary) from manager);

select ename ,salary,annualsalary from manager
where salary = (select min(salary) from manager);

select avg(salary) from manager;
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/fc9f18c8-8abb-4422-b43c-7fa4df53e146)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.
### QUERY:
```
SELECT designation, COUNT(*) AS "Number of Employees"
FROM manager
GROUP BY designation
ORDER BY COUNT(*) DESC;
```
### OUTPUT:

![image](https://github.com/Safeeq-Fazil/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118680361/f2afee95-08a0-4f4b-9418-c80fecd6625b)


### RESULT:
Thus, Manager database is created and DML queries such as insertion, updation, deletion are executed using SQL.
