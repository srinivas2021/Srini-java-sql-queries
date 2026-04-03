# Srini-java-sql-queries
1) SQL Query to Delete Duplicate Rows:

DELETE FROM Employees
WHERE EmployeeID NOT IN (
    SELECT MIN(EmployeeID)
    FROM Employees
    GROUP BY Name, Department
);

2) Highest Salary from Employee table:

Select salary from employee ORDER BY salary DESC LIMIT 0,1; 
Select salary from employee ORDER BY salary DESC LIMIT 1,1; //2nd highest
