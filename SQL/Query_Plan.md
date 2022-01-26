SQL Batch               -> Parsing      -> Parse Tree
Parse Tree              -> Algebrizer   -> Query Processor Tree
Query Processor Tree    -> Opitimizer   -> Plan into Procedure Cache

Parsing
- Checks syntax, grammar

Algebrizer

- Binding
Determines characteristics of objects referenced in SQL e.g. FROM A join B will fail if B is stored proc.
1. Name resolution from system catalogue.
2. Special binding -  aggregates and groupings.

3. Binary operator flattening.

Optimiser

Statements optimised:
DML
DDL: Create Index, Create/Update Statistics, Some alter index, Some internal commands within DBCC CHECKDB
Only Create Index produces a showplan with a statistics profile. None produce a plan in SSMS.

________________________________________

### Poor indexing
- Indexes to serve the need of the queries.

### Inaccurate statistics
- Need accurate estimates as to the amount of data to be retrieved.

### Excessive blocking and deadlocks

### Poor query design

### Poor database design

### Excessive fragmentation

### Nonreusable execution plans

### Frequent recompilation of execution plans

### Improper use of cursors

### Improper configuration of the database log

### Ineffective connection pooling 
