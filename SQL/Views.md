# Views
https://docs.microsoft.com/en-us/sql/relational-databases/views/views?view=sql-server-ver15

- Virtual table
- Defined by a query
  - multiple tables
- Indexed view materialised
- Simplifies access to disparate data
- Security
- Backwards compatibility - a table that no longer exists

## Types
### Indexed
- Materialised
- Preferred for slow changing data

### Partitioned
- Joins horizontally partitioned data across servers
  -  Local partitioned view - single sever

### System View
- Catalog metadata
