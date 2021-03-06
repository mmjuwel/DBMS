SQL Queries for Software Testers

SQL Queries for Software Testers, Database Fundamentals, Database Engine Installation, SQL Language Elements, Data Definition Language, Data Manipulation language, and Data Control language. SQL Views, SQL Keys, SQL Indexes, and Database Normalization.

sql tutorial
SQL Queries for Software Testers

Create the following Tables:
LOCATION
Location_ID	Regional_Group
122	NEW YORK
123	DALLAS
124	CHICAGO
167	BOSTON
 

DEPARTMENT
Department_ID	Name	Location_ID
10	ACCOUNTING	122
20	RESEARCH	124
30	SALES	123
40	OPERATIONS	167
 

JOB
Job_ID	Function
667	CLERK
668	STAFF
669	ANALYST
670	SALESPERSON
671	MANAGER
672	PRESIDENT
 

EMPLOYEE
EMPLOYEE_ID	LAST_NAME	FIRST_NAME	MIDDLE_NAME	JOB_ID	MANAGER_ID	HIREDATE	SALARY	COMM	DEPARTMENT_ID
7369	SMITH	JOHN	Q	667	7902	17-DEC-84	800	NULL	20
7499	ALLEN	KEVIN	J	670	7698	20-FEB-85	1600	300	30
7505	DOYLE	JEAN	K	671	7839	04-APR-85	2850	NULL	30
7506	DENNIS	LYNN	S	671	7839	15-MAY-85	2750	NULL	30
7507	BAKER	LESLIE	D	671	7839	10-JUN-85	2200	NULL	40
7521	WARK	CYNTHIA	D	670	7698	22-FEB-85	1250	500	30
Queries based on the above tables:
Simple Queries:
1) List all the employee details

2) List all the department details

3) List all job details

4) List all the locations

5) List out first name,last name,salary, commission for all employees

6) List out employee_id,last name,department id for all employees and rename employee id as “ID of the employee”, last name as “Name of the employee”, department id as “department ID”

7) List out the employees annual salary with their names only.

Where Conditions:
8) List the details about “SMITH”

9) List out the employees who are working in department 20

10) List out the employees who are earning salary between 3000 and 4500

11) List out the employees who are working in department 10 or 20

12) Find out the employees who are not working in department 10 or 30

13) List out the employees whose name starts with “S”

14) List out the employees whose name start with “S” and end with “H”

15) List out the employees whose name length is 4 and start with “S”

16) List out the employees who are working in department 10 and draw the salaries more than 3500

17) list out the employees who are not receiving commission.

Order By Clause:
18) List out the employee id, last name in ascending order based on the employee id.

19) List out the employee id, name in descending order based on salary column

20) list out the employee details according to their last_name in ascending order and salaries in descending order

21) list out the employee details according to their last_name in ascending order and then on department_id in descending order.

Group By & Having Clause:
22) How many employees who are working in different departments wise in the organization

23) List out the department wise maximum salary, minimum salary, average salary of the employees

24) List out the job wise maximum salary, minimum salary, average salaries of the employees.

25) List out the no.of employees joined in every month in ascending order.

26) List out the no.of employees for each month and year, in the ascending order based on the year, month.

27) List out the department id having atleast four employees.

28) How many employees in January month.

29) How many employees who are joined in January or September month.

30) How many employees who are joined in 1985.

31) How many employees joined each month in 1985.

32) How many employees who are joined in March 1985.

33) Which is the department id, having greater than or equal to 3 employees joined in April 1985.

Sub-Queries
34) Display the employee who got the maximum salary.

35) Display the employees who are working in Sales department

36) Display the employees who are working as “Clerk”.

37) Display the employees who are working in “New York”

38) Find out no.of employees working in “Sales” department.

39) Update the employees salaries, who are working as Clerk on the basis of 10%.

40) Delete the employees who are working in accounting department.

41) Display the second highest salary drawing employee details.

42) Display the Nth highest salary drawing employee details

Sub-Query operators: (ALL,ANY,SOME,EXISTS)
43) List out the employees who earn more than every employee in department 30.

44) List out the employees who earn more than the lowest salary in department 30.

45) Find out whose department has not employees.

46) Find out which department does not have any employees.

Co-Related Sub Queries:

47) Find out the employees who earn greater than the average salary for their department.

JOINS
Simple join
48) List our employees with their department names

49) Display employees with their designations (jobs)

50) Display the employees with their department name and regional groups.

51) How many employees who are working in different departments and display with department name.

52) How many employees who are working in sales department.

53) Which is the department having greater than or equal to 5 employees and display the department names in ascending order.

54) How many jobs in the organization with designations.

55) How many employees working in “New York”.

Non – Equi Join:
56) Display employee details with salary grades.

57) List out the no. of employees on grade wise.

58) Display the employ salary grades and no. of employees between 2000 to 5000 range of salary.

Self Join:
59) Display the employee details with their manager names.

60) Display the employee details who earn more than their managers salaries.

61) Show the no. of employees working under every manager.

Outer Join:
62) Display employee details with all departments.

63) Display all employees in sales or operation departments.

Set Operators:
64) List out the distinct jobs in Sales and Accounting Departments.

65) List out the ALL jobs in Sales and Accounting Departments.

66) List out the common jobs in Research and Accounting Departments in ascending order.

Answers
1) SQL > Select * from employee;

2) SQL > Select * from department;

3) SQL > Select * from job;

4) SQL > Select * from loc;

5) SQL > Select first_name, last_name, salary, commission from employee;

6) SQL > Select employee_id “id of the employee”, last_name “name”, department id as “department id” from employee;

7) SQL > Select last_name, salary*12 “annual salary” from employee

8) SQL > Select * from employee where last_name=’SMITH’;

9) SQL > Select * from employee where department_id=20

10) SQL > Select * from employee where salary between 3000 and 4500

11) SQL > Select * from employee where department_id in (20,30)

12) SQL > Select last_name, salary, commission, department_id from employee where department_id not in (10,30)

13) SQL > Select * from employee where last_name like ‘S%’

14) SQL > Select * from employee where last_name like ‘S%H’

15) SQL > Select * from employee where last_name like ‘S___’

16) SQL > Select * from employee where department_id=10 and salary>3500

17) SQL > Select * from employee where commission is Null

18) SQL > Select employee_id, last_name from employee order by employee_id

19) SQL > Select employee_id, last_name, salary from employee order by salary desc

20) SQL > Select employee_id, last_name, salary from employee order by last_name, salary desc

21) SQL > Select employee_id, last_name, salary from employee order by last_name, department_id desc

22) SQL > Select department_id, count(*), from employee group by department_id

23) SQL > Select department_id, count(*), max(salary), min(salary), avg(salary) from employee group by department_id

24) SQL > Select job_id, count(*), max(salary), min(salary), avg(salary) from employee group by job_id

25) SQL > Select to_char(hire_date,’month’)month, count(*) from employee group by to_char(hire_date,’month’) order by month

26) SQL > Select to_char(hire_date,’yyyy’) Year, to_char(hire_date,’mon’) Month, count(*) “No. of employees” from employee group by to_char(hire_date,’yyyy’), to_char(hire_date,’mon’)

27) SQL > Select department_id, count(*) from employee group by department_id having count(*)>=4

28) SQL > Select to_char(hire_date,’mon’) month, count(*) from employee group by to_char(hire_date,’mon’) having to_char(hire_date,’mon’)=’jan’

29) SQL > Select to_char(hire_date,’mon’) month, count(*) from employee group by to_char(hire_date,’mon’) having to_char(hire_date,’mon’) in (‘jan’,’sep’)

30) SQL > Select to_char(hire_date,’yyyy’) Year, count(*) from employee group by to_char(hire_date,’yyyy’) having to_char(hire_date,’yyyy’)=1985

31) SQL > Select to_char(hire_date,’yyyy’)Year, to_char(hire_date,’mon’) Month, count(*) “No. of employees” from employee where to_char(hire_date,’yyyy’)=1985 group by to_char(hire_date,’yyyy’),to_char(hire_date,’mon’)

32) SQL > Select to_char(hire_date,’yyyy’)Year, to_char(hire_date,’mon’) Month, count(*) “No. of employees” from employee where to_char(hire_date,’yyyy’)=1985 and to_char(hire_date,’mon’)=’mar’ group by to_char(hire_date,’yyyy’),to_char(hire_date,’mon’)

33) SQL > Select department_id, count(*) “No. of employees” from employee where to_char(hire_date,’yyyy’)=1985 and to_char(hire_date,’mon’)=’apr’ group by to_char(hire_date,’yyyy’), to_char(hire_date,’mon’), department_id having count(*)>=3

34) SQL > Select * from employee where salary=(select max(salary) from employee)

35) SQL > Select * from employee where department_id IN (select department_id from department where name=’SALES’)

36) SQL > Select * from employee where job_id in (select job_id from job where function=’CLERK’

37) SQL > Select * from employee where department_id=(select department_id from department where location_id=(select location_id from location where regional_group=’New York’))

38) SQL > Select * from employee where department_id=(select department_id from department where name=’SALES’ group by department_id)

39) SQL > Update employee set salary=salary*10/100 wehre job_id=(select job_id from job where function=’CLERK’)

40) SQL > delete from employee where department_id=(select department_id from department where name=’ACCOUNTING’)

41) SQL > Select * from employee where salary=(select max(salary) from employee where salary <(select max(salary) from employee))

42) SQL > Select distinct e.salary from employee where & no-1=(select count(distinct salary) from employee where sal>e.salary)

43) SQL > Select * from employee where salary > all (Select salary from employee where department_id=30)

44) SQL > Select * from employee where salary > any (Select salary from employee where department_id=30)

45) SQL > Select employee_id, last_name, department_id from employee e where not exists (select department_id from department d where d.department_id=e.department_id)

46) SQL > Select name from department d where not exists (select last_name from employee e where d.department_id=e.department_id)

47) SQL > Select employee_id, last_name, salary, department_id from employee e where salary > (select avg(salary) from employee where department_id=e.department_id)

48) SQL > Select employee_id, last_name, name from employee e, department d where e.department_id=d.department_id

49) SQL > Select employee_id, last_name, function from employee e, job j where e.job_id=j.job_id

50) SQL > Select employee_id, last_name, name, regional_group from employee e, department d, location l where e.department_id=d.department_id and d.location_id=l.location_id

51) SQL > Select name, count(*) from employee e, department d where d.department_id=e.department_id group by name

52) SQL > Select name, count(*) from employee e, department d where d.department_id=e.department_id group by name having name=’SALES’

53) SQL > Select name, count(*) from employee e, department d where d.department_id=e.department_id group by name having count (*)>=5 order by name

54) SQL > Select function, count(*) from employee e, job j where j.job_id=e.job_id group by function

55) SQL > Select regional_group, count(*) from employee e, department d, location l where e.department_id=d.department_id and d.location_id=l.location_id and regional_group=’NEW YORK’ group by regional_group

56) SQL > Select employee_id, last_name, grade_id from employee e, salary_grade s where salary between lower_bound and upper_bound order by last_name

57) SQL > Select grade_id, count(*) from employee e, salary_grade s where salary between lower_bound and upper_bound group by grade_id order by grade_id desc

58) SQL > Select grade_id, count(*) from employee e, salary_grade s where salary between lower_bound and upper_bound and lower_bound>=2000 and lower_bound<=5000 group by grade_id order by grade_id desc

59) SQL > Select e.last_name emp_name, m.last_name, mgr_name from employee e, employee m where e.manager_id=m.employee_id

60) SQL > Select e.last_name emp_name, e.salary emp_salary, m.last_name, mgr_name, m.salary mgr_salary from employee e, employee m where e.manager_id=m.employee_id and m.salary

61) SQL > Select m.manager_id, count(*) from employee e, employee m where e.employee_id=m.manager_id group by m.manager_id

62) SQL > Select last_name, d.department_id, d.name from employee e, department d where e.department_id(+)=d.department_id

63) SQL > Select last_name, d.department_id, d.name from employee e, department d where e.department_id(+)=d.department_id and d.department_idin (select department_id from department where name IN (‘SALES’,’OPERATIONS’))

64) SQL > Select function from job where job_id in (Select job_id from employee where department_id=(select department_id from department where name=’SALES’)) union Select function from job where job_id in (Select job_id from employee where department_id=(select department_id from department where name=’ACCOUNTING’))

65) SQL > Select function from job where job_id in (Select job_id from employee where department_id=(select department_id from department where name=’SALES’)) union all Select function from job where job_id in (Select job_id from employee where department_id=(select department_id from department where name=’ACCOUNTING’))

66) SQL > Select function from job where job_id in (Select job_id from employee where department_id=(select department_id from department where name=’RESEARCH’)) intersect Select function from job where job_id in (Select job_id from employee where department_id=(select department_id from department where name=’ACCOUNTING’)) order by function
