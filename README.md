# end to end interview 
https://github.com/yashprogrammer/ReAct_agent.git
https://github.com/krishnaik06/Complete-RoadMap-To-Learn-AI.git
16. What are constraints in SQL?
Constraints enforce rules on data.
Types:
NOT NULL → column cannot be NULL
UNIQUE → values must be unique
PRIMARY KEY → uniquely identifies row
FOREIGN KEY → creates relationship
CHECK → ensures condition
DEFAULT → default value
17. What is a subquery?
A subquery is a query inside another query.
Types:
Scalar Subquery
Column Subquery
Row Subquery
Table Subquery
Correlated Subquery
18. What are relationships in SQL?
Relationships connect tables using keys.
Types:
One-to-One
One-to-Many
Many-to-Many
19. What is NULL?
NULL represents missing or unknown data.
It is not equal to 0 or empty string.
20. Difference between SQL and NoSQL
SQL:
Structured
Table-based
Relational database
NoSQL:
Unstructured / semi-structured
Document or key-value based
Flexible and scalable
21. Challenges with SQL databases
Limited scalability for big data
Complex joins reduce performance
Schema changes are difficult
Maintaining distributed consistency
22. Window Functions
Window functions perform calculations across rows.
Example:
SQL
Copy code
SELECT EmployeeID,
       Salary,
       RANK() OVER (ORDER BY Salary DESC) AS SalaryRank
FROM Employees;
Other functions:
Copy code

ROW_NUMBER()
LAG()
LEAD()
SUM() OVER()
23. Common Table Expressions (CTE)
Temporary result set using WITH.
Example:
SQL
Copy code
WITH HighSales AS (
    SELECT DepartmentID, SUM(Sales) AS TotalSales
    FROM SalesData
    GROUP BY DepartmentID
)

SELECT *
FROM HighSales
WHERE TotalSales > 50000;
24. Normalization
Normalization organizes data to reduce redundancy.
Types:
1NF
2NF
3NF
BCNF
4NF
5NF
25. Denormalization
Denormalization adds redundancy to improve read performance.
Normalization → data integrity
Denormalization → faster queries
26. Indexing in SQL
Indexing speeds up query performance by avoiding full table scans.
Types:
Clustered Index
Non-Clustered Index
27. SQL Functions
Functions perform tasks and return values.
Types:
Aggregate functions
Scalar functions
Case manipulation functions
28. Aggregate Functions
Operate on a set of values.
Examples:
Copy code

COUNT()
SUM()
AVG()
MAX()
MIN()
29. Scalar Functions
Operate on a single value.
Examples:
Copy code

UPPER()
LOWER()
ROUND()
LEN()
30. Character Manipulation Functions
Examples:
Copy code

LENGTH()
SUBSTRING()
CONCAT()
TRIM()
31. Difference between SQL and PL/SQL
SQL:
Query language
PL/SQL:
Procedural extension of SQL
Supports loops, conditions, error handling
32. Stored Procedure vs Function
Stored Procedure
Performs tasks
May or may not return value
Function
Must return a value
Used in expressions
33. ORDER BY default
Default order is Ascending.
Descending example:
SQL
Copy code
SELECT * 
FROM Students
ORDER BY Age DESC;
34. Set Operators
Copy code

UNION
UNION ALL
INTERSECT
MINUS / EXCEPT
35. Pattern Matching
Operator used:
Copy code

LIKE
Example:
SQL
Copy code
SELECT * FROM Students
WHERE Name LIKE 'A%';
36. Composite Primary Key
Primary key made of multiple columns.
Example:
Copy code

PRIMARY KEY (OrderID, ProductID)
37. What is a View?
A view is a virtual table created from a query.
Uses:
Simplify queries
Improve security
Present data differently
38. DELETE vs TRUNCATE
DELETE
Removes specific rows
Can be rolled back
TRUNCATE
Removes all rows
Faster
Cannot rollback
39. DROP vs TRUNCATE
DROP
Deletes table structure and data
TRUNCATE
Deletes only data
Keeps structure
40. HAVING vs WHERE
WHERE:
Filters rows before grouping
HAVING:
Filters groups after aggregation
Example:
SQL
Copy code
SELECT department, COUNT(*)
FROM Employees
GROUP BY department
HAVING COUNT(*) > 5;
