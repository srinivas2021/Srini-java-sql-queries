# Srini-java-sql-queries
1) **SQL Query to Delete Duplicate Rows:**

DELETE FROM Employees
WHERE EmployeeID NOT IN (
    SELECT MIN(EmployeeID)
    FROM Employees
    GROUP BY Name, Department
);

2) **Identify Duplicate Records**

SELECT a.*
FROM table_name a
JOIN table_name b ON a.duplicate_column = b.duplicate_column
WHERE a.id <> b.id;

SELECT GeekRank, COUNT(GeekID) AS DuplicateRanks
FROM Geeks
GROUP BY GeekRank
HAVING COUNT(GeekRank)>1; 

3) **Highest Salary from Employee table:**

Select salary from employee ORDER BY salary DESC LIMIT 0,1; 

Select salary from employee ORDER BY salary DESC LIMIT 1,1; //2nd highest

CREATE TABLE Products (
  product_id int,
  name varchar(50),
  status varchar(20),
  updated_at date
);

INSERT INTO Products(product_id,name,status,updated_at) VALUES (1, 'Laptop', 'OnDelivery','2026-04-09');
INSERT INTO Products(product_id,name,status,updated_at) VALUES (2, 'mobile', 'inprogress','2026-04-10');
INSERT INTO Products(product_id,name,status,updated_at) VALUES (3, 'mouse', 'Delivered','2026-04-09');
INSERT INTO Products(product_id,name,status,updated_at) VALUES (4, 'lamp', 'Delivered','2026-04-10');
INSERT INTO Products(product_id,name,status,updated_at) VALUES (5, 'Camera', 'Delivered','2026-04-10');

**To fetch today's products:**

SELECT product_id, name, status, updated_at 
FROM Products WHERE CONVERT(DATE, updated_at) = CONVERT(DATE, GETDATE());
