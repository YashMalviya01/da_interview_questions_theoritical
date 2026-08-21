Data Analyst Interview Preparation
SQL Phase 2 — 15 Theory Questions + Answers
Study these answers first, then practice the questions from memory without looking at the answers.
/* 1. Query Execution Plan */
An execution plan is the roadmap the database engine uses to execute a SQL query. It shows how data is retrieved and processed, including scans, indexes, joins, sorting, and filtering.
Interview answer: An execution plan shows how the database engine intends to execute a query. I use it to identify expensive operations, check index usage, and understand joins, scans, and filters.
/* 2. Indexing in SQL */
An index is a database structure that helps locate rows efficiently instead of scanning the entire table.
Example:
CREATE INDEX idx_employee_email
ON Employees(Email);
Interview answer: An index improves data retrieval, but consumes storage and can add overhead to write operations.
/* 3. Table Partitioning */
Table partitioning divides a large table into smaller logical partitions based on a partition key such as date. It can improve performance when queries can access only relevant partitions.
Interview answer: Partitioning divides a large table into smaller partitions based on a key such as date, allowing relevant queries to potentially scan only the necessary partitions.
/* 4. Deadlock in SQL */
A deadlock occurs when transactions hold locks that other transactions need, creating a circular wait.
Reduce deadlocks by: accessing resources in a consistent order, keeping transactions short, avoiding unnecessary locks, using appropriate indexes, and breaking large transactions into smaller batches.
/* 5. EXISTS in SQL */
EXISTS checks whether a subquery returns at least one row.
Example:
SELECT c.CustomerID, c.CustomerName
FROM Customers c
WHERE EXISTS (
SELECT 1
FROM Orders o WHERE o.CustomerID = c.CustomerID
);
/* 6. Dynamic SQL */
Dynamic SQL constructs and executes SQL statements at runtime.
Example:
DECLARE @SQL NVARCHAR(MAX); SET @SQL = 'SELECT * FROM Employees WHERE DepartmentID = @DeptID';
EXEC sp_executesql @SQL, N'@DeptID INT', @DeptID = 10;
Important: Parameterized execution should be used to reduce SQL-injection risk.
/* 7. Stored Procedure vs Function */
A stored procedure is a stored program that can perform operations and may return result sets or output parameters. A function returns a value or table, depending on the database system, and is commonly used for reusable calculations or logic.
Key distinction: Procedures are commonly used for operations/workflows; functions are commonly used to return reusable values or table results.
/* 8. OLTP vs OLAP */
OLTP: Online Transaction Processing; operational workloads such as orders, payments, and banking transactions.
Many small transactions and frequent INSERT/UPDATE/DELETE operations.
OLAP: Online Analytical Processing; analytical workloads such as sales analysis, BI reporting, aggregations, and historical analysis. Generally read-heavy and designed for large data volumes.
Interview answer: OLTP supports day-to-day transactions, while OLAP supports analytical and reporting workloads.
/* 9. How do you optimize SQL queries? */
I would approach optimization systematically:
1.	Identify the slow query.
2.	Examine the execution plan.
3.	Identify the bottleneck.
4.	Check indexes.
5.	Review joins and filters.
6.	Reduce unnecessary data.
7.	Test the change.
8.	Compare performance.
The key is to identify the bottleneck before changing the query or database structure.
/* 10. How do you improve SQL query performance? */
First determine why the query is slow. Investigate the execution plan, table scans, index usage, joins, filtering, sorting, and rows processed.
Example:
SELECT EmpID, EmpName, Salary
FROM Employees
WHERE DepartmentID = 10;
Select only required columns and make targeted improvements based on the execution plan.
/* 11. Composite Index */
A composite index is an index created on multiple columns.
Example:
CREATE INDEX idx_dept_salary
ON Employees(DepartmentID, Salary);
Interview point: Column order matters because the leading column affects how the index can be efficiently used.
/* 12. Query Optimization */
Query optimization is the process of finding an efficient execution strategy for a SQL query. The optimizer evaluates factors such as indexes, join methods, filtering, data distribution, and estimated row counts.
Interview answer: Query optimization selects an efficient execution strategy based on the database's available information and possible execution plans.
/* 13. Clustered vs Non-clustered Index */
Clustered index: organizes the table's stored data around the index key, according to the database engine's implementation.
Non-clustered index: a separate index structure that points to the underlying rows.
Interview answer: A clustered index organizes stored table data around the key, whereas a non-clustered index is a separate structure pointing to rows. Exact behavior depends on the database system.
/* 14. SQL Transaction */
A transaction is a logical unit of database work consisting of one or more SQL operations.
Example:
BEGIN;
UPDATE Accounts
SET Balance = Balance - 1000
WHERE AccountID = 1;
UPDATE Accounts
SET Balance = Balance + 1000 WHERE AccountID = 2;
COMMIT;
If the transaction cannot complete correctly, it can be rolled back.
/* 15. ACID Properties */
Atomicity: the transaction is treated as one unit.
Consistency: the transaction moves the database between valid states.
Isolation: concurrent transactions should not improperly interfere with each other.
Durability: committed changes should persist after failures.
Interview answer: ACID stands for Atomicity, Consistency, Isolation, and Durability; these properties provide reliable and integrity-preserving transactions.
<img width="521" height="677" alt="image" src="https://github.com/user-attachments/assets/36cf79f8-121d-40f3-83ba-64f4eb149805" />
