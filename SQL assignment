//EmployeeDetails table//
 ==>CREATE TABLE EmployeeDetails (    EmpId int PRIMARY KEY,    FullName varchar(50) NOT NULL,    ManagerId int,    DateOfJoining date NOT NULL,    City varchar(50) NOT NULL);

==>INSERT INTO EmployeeDetails (EmpId, FullName, ManagerId, DateOfJoining, City) VALUES(1, 'John ', NULL, '2020-01-01', 'Chennai'),(2, 'Anitha', 1, '2020-02-01', 'Banglore'),(3, 'Bhanu', 1, '2021-03-01', 'Chennai'),(4, 'Satya', 3, '2020-04-01', 'Hyderabad'),(5, 'David', 2, '2022-01-01', 'Banglore');
==>SELECT * FROM EmployeeDetails;

//EmployeeSalary table //
=> CREATE TABLE EmployeeSalary (    EmpId int PRIMARY KEY,    Project varchar(50) NOT NULL,    Salary float NOT NULL,    Variable float NOT NULL);

=>INSERT INTO EmployeeSalary (EmpId, Project, Salary, Variable) VALUES(1, 'Project A', 50000, 10000),(2, 'Project B', 60000, 12000),(4, 'Project C', 70000, 14000);
=> SELECT * FROM EmployeeSalary


1Q.SQL Query to fetch records that are present in one table but not in another table.
==> SELECT EmpId FROM  EmployeeDetails WHERE EmpId NOT IN (SELECT EmpId FROM EmployeeSalary);

2Q.SQL query to fetch all the employees who are not working on any project.
==> SELECT FullName FROM  EmployeeDetails WHERE  EmpId NOT IN (SELECT EmpId FROM EmployeeSalary WHERE Project IS NOT NULL);

3Q.SQL query to fetch all the Employees from EmployeeDetails who joined in the Year 2020.
==>SELECT * FROM  EmployeeDetails WHERE DateOfJoining BETWEEN '2020-01-01' and '2020-12-31';

4Q.Fetch all employees from EmployeeDetails who have a salary record in EmployeeSalary.
==>SELECT DISTINCT ed.* FROM EmployeeDetails ed INNER JOIN EmployeeSalary es ON ed.EmpId = es.EmpId;

5Q.Write an SQL query to fetch a project-wise count of employees.
==> SELECT Project,COUNT(*) AS CountofEmployees FROM EmployeeSalary GROUP BY Project;

6Q.Fetch employee names and salaries even if the salary value is not present for the employee.
==> SELECT ed.FullName,COALESCE(es.Salary,0) AS Salary FROM EmployeeDetails ed LEFT JOIN EmployeeSalary es ON ed.EmpId = es.EmpId;

7Q.Write an SQL query to fetch all the Employees who are also managers.
==>SELECT ed.FullName FROM EmployeeDetails ed INNER JOIN EmployeeDetails ed1 ON ed.EmpId = ed1.ManagerId;

8Q.Write an SQL query to fetch duplicate records from EmployeeDetails.
==>SELECT EmpId, FullName, COUNT(*) AS Count FROM EmployeeDetails GROUP BY EmpId,FullName HAVING COUNT(*) > 1;

9Q.Write an SQL query to fetch only odd rows from the table.
==> SELECT * FROM  EmployeeDetails WHERE EmpId IN (SELECT EmpId FROM (SELECT EmpId,ROW_NUMBER() OVER (ORDER BY EmpId) AS RowNum FROM EmployeeDetails ) AS Temp WHERE Temp.RowNum % 2 <> 0);

10Q.Write a query to find the 3rd highest salary from a table without top or limit keyword.
==>SELECT DISTINCT Salary FROM EmployeeSalary es1 WHERE 3 = (SELECT Salary) FROM EmployeeSalary es2.Salary > es1.Salary;
