# SQL Phase 2 — 15 Theory Questions & Answers

> **Data Analyst Interview Preparation**
>
> Phase 2 SQL theory practice. Review the answers first, then practice the questions from memory without looking at the answers.

---

## /* 1. Query Execution Plan */

### Question

What is a Query Execution Plan?

### Answer

A **Query Execution Plan** is the roadmap the database engine uses to execute a SQL query. It shows how data is retrieved and processed, including operations such as:

- Table scans
- Index usage
- Joins
- Sorting
- Filtering

**Interview answer:**

> An execution plan shows how the database engine intends to execute a query. I use it to identify expensive operations, check index usage, and understand joins, scans, and filters.

---

## /* 2. Indexing in SQL */

### Question

What is Indexing in SQL?

### Answer

An **index** is a database structure that helps locate rows efficiently instead of scanning the entire table.

```sql
CREATE INDEX idx_employee_email
ON Employees(Email);
```

**Interview answer:**

> An index improves data retrieval, but it consumes storage and can add overhead to write operations.

---

## /* 3. Table Partitioning */

### Question

What is Table Partitioning?

### Answer

**Table partitioning** divides a large table into smaller logical partitions based on a partition key such as date.

It can improve performance when queries can access only relevant partitions instead of scanning the entire table.

**Interview answer:**

> Partitioning divides a large table into smaller partitions based on a key such as date, allowing relevant queries to potentially scan only the necessary partitions.

---

## /* 4. Deadlock in SQL */

### Question

What is a Deadlock in SQL?

### Answer

A **deadlock** occurs when transactions hold locks that other transactions need, creating a circular wait.

Ways to reduce deadlocks include:

1. Access resources in a consistent order.
2. Keep transactions short.
3. Avoid unnecessary locks.
4. Use appropriate indexes.
5. Break large transactions into smaller batches.

**Interview answer:**

> A deadlock occurs when transactions hold locks that other transactions need, creating a circular wait. I would reduce deadlocks by keeping transactions short, accessing resources in a consistent order, using appropriate indexes, and minimizing unnecessary locking.

---

## /* 5. EXISTS in SQL */

### Question

What is the use of `EXISTS` in SQL?

### Answer

`EXISTS` checks whether a subquery returns at least one row.

```sql
SELECT
    c.CustomerID,
    c.CustomerName
FROM Customers c
WHERE EXISTS (
    SELECT 1
    FROM Orders o
    WHERE o.CustomerID = c.CustomerID
);
```

`EXISTS` is useful when we only need to determine whether a related record exists.

---

## /* 6. Dynamic SQL */

### Question

What is Dynamic SQL?

### Answer

**Dynamic SQL** constructs and executes SQL statements at runtime.

```sql
DECLARE @SQL NVARCHAR(MAX);

SET @SQL = '
    SELECT *
    FROM Employees
    WHERE DepartmentID = @DeptID
';

EXEC sp_executesql
    @SQL,
    N'@DeptID INT',
    @DeptID = 10;
```

**Important:** Parameterized execution should be used to reduce SQL-injection risk.

**Interview answer:**

> Dynamic SQL allows SQL statements to be constructed and executed at runtime. It can be useful when the query structure needs to vary dynamically, but I would use parameterized execution to reduce SQL-injection risks.

---

## /* 7. Stored Procedure vs Function */

### Question

What is the difference between a Stored Procedure and a Function?

### Answer

A **stored procedure** is a stored program that can perform operations and may return result sets or output parameters.

A **function** returns a value or table, depending on the database system, and is commonly used for reusable calculations or logic.

**Key distinction:**

| Stored Procedure | Function |
|---|---|
| Commonly used for operations/workflows | Commonly used for reusable values/logic |
| May return result sets/output parameters | Returns a value or table |
| Invocation syntax varies by DBMS | Can often be used in expressions |

---

## /* 8. OLTP vs OLAP */

### Question

What is the difference between OLTP and OLAP?

### Answer

### OLTP — Online Transaction Processing

Designed for operational workloads such as:

- Orders
- Payments
- Banking transactions
- Inventory updates

Typical characteristics:

- Many small transactions
- Frequent `INSERT` / `UPDATE` / `DELETE`
- High concurrency
- Usually normalized operational data

### OLAP — Online Analytical Processing

Designed for analytical workloads such as:

- Sales analysis
- BI reporting
- Aggregations
- Historical analysis

Typical characteristics:

- Complex analytical queries
- Large data volumes
- Aggregations
- Read-heavy workloads
- Historical analysis

**Interview answer:**

> OLTP systems support day-to-day transactional operations, while OLAP systems are designed for analytical workloads such as reporting, aggregations, and historical business analysis.

---

## /* 9. How do you optimize SQL queries? */

### Question

How do you optimize SQL queries?

### Answer

I would approach optimization systematically:

1. Identify the slow query.
2. Examine the execution plan.
3. Identify the bottleneck.
4. Check indexes.
5. Review joins and filters.
6. Reduce unnecessary data.
7. Test the change.
8. Compare performance.

Common techniques include:

- Selecting only required columns
- Using appropriate indexes
- Optimizing joins
- Avoiding inefficient filtering
- Reducing unnecessary scans
- Using execution plans

**Interview answer:**

> I would first identify the bottleneck using the execution plan, then make a targeted optimization and benchmark the result to verify that performance actually improved.

---

## /* 10. How do you improve SQL query performance? */

### Question

How do you improve SQL query performance?

### Answer

First, determine **why** the query is slow.

Investigate:

- Execution plan
- Table scans
- Index usage
- Join operations
- Filtering
- Sort operations
- Number of rows processed

Example:

```sql
SELECT
    EmpID,
    EmpName,
    Salary
FROM Employees
WHERE DepartmentID = 10;
```

Selecting only required columns can reduce unnecessary data processing compared with:

```sql
SELECT *
FROM Employees
WHERE DepartmentID = 10;
```

**Interview answer:**

> I first identify the bottleneck using the execution plan, then optimize the specific issue—for example, improving indexing, reducing unnecessary columns or rows, or optimizing joins and filters. Finally, I benchmark the revised query to verify the improvement.

---

## /* 11. Composite Index */

### Question

What is a Composite Index?

### Answer

A **composite index** is an index created on multiple columns.

```sql
CREATE INDEX idx_dept_salary
ON Employees(DepartmentID, Salary);
```

It can be useful when queries frequently filter or sort using those columns.

**Important interview point:**

> Column order matters because the leading column affects how the index can be efficiently utilized.

---

## /* 12. Query Optimization */

### Question

What is Query Optimization?

### Answer

**Query optimization** is the process of finding an efficient execution strategy for a SQL query.

The optimizer can evaluate factors such as:

- Available indexes
- Join methods
- Data distribution
- Filtering
- Estimated row counts
- Sorting

**Interview answer:**

> Query optimization is the process of selecting an efficient execution strategy for a SQL query. The optimizer evaluates factors such as indexes, joins, filters, and estimated row counts to determine an efficient execution plan.

---

## /* 13. Clustered vs Non-clustered Index */

### Question

What is the difference between a Clustered and Non-clustered Index?

### Answer

### Clustered Index

A clustered index organizes the table's stored data around the index key, according to the database engine's implementation.

### Non-clustered Index

A non-clustered index is a separate index structure that points to the underlying rows.

**Interview answer:**

> A clustered index organizes stored table data around the key, whereas a non-clustered index is a separate structure pointing to rows. The exact behavior depends on the database system.

---

## /* 14. SQL Transaction */

### Question

What is a Transaction in SQL?

### Answer

A **transaction** is a logical unit of database work consisting of one or more SQL operations.

Example:

```sql
BEGIN;

UPDATE Accounts
SET Balance = Balance - 1000
WHERE AccountID = 1;

UPDATE Accounts
SET Balance = Balance + 1000
WHERE AccountID = 2;

COMMIT;
```

If the transaction cannot complete correctly, it can be rolled back:

```sql
ROLLBACK;
```

---

## /* 15. ACID Properties */

### Question

What are ACID Properties in SQL?

### Answer

ACID describes the fundamental properties expected from reliable database transactions.

| Property | Meaning |
|---|---|
| **Atomicity** | The transaction is treated as one unit. |
| **Consistency** | The transaction moves the database between valid states. |
| **Isolation** | Concurrent transactions should not improperly interfere with each other. |
| **Durability** | Committed changes should persist after failures. |

**Interview answer:**

> ACID stands for Atomicity, Consistency, Isolation, and Durability. These properties ensure that database transactions are reliable, maintain data integrity, handle concurrency correctly, and preserve committed changes.

---

# Today's SQL Theory Checklist

- [ ] Query Execution Plan
- [ ] Indexing
- [ ] Table Partitioning
- [ ] Deadlocks
- [ ] `EXISTS`
- [ ] Dynamic SQL
- [ ] Stored Procedure vs Function
- [ ] OLTP vs OLAP
- [ ] SQL Query Optimization
- [ ] Query Performance
- [ ] Composite Index
- [ ] Query Optimization Concept
- [ ] Clustered vs Non-clustered Index
- [ ] Transactions
- [ ] ACID Properties

**15 / 15 — SQL Phase 2 Theory Complete**
