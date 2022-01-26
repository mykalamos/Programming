https://docs.microsoft.com/en-us/sql/relational-databases/indexes/clustered-and-nonclustered-indexes-described?view=sql-server-ver15

- On-disk structure for table/view that speeds retreival of rows
- Composed of keys built from 1+ columns
- Stored in B-Tree

## Clustered
- Sort and store based on values
- Only one per table
- No clustered index = heap (unordered)
  - Leaf nodes are table data
- 
## Nonclustered
- Separate from data
- Pointer to data row => Row Locator
  - Heap = Pointer to row
  - Clustered Table = Clustered Index Key

- Indexes can be unique
- Automatically maintained on modification
- Created when ``` PRIMARY KEY ``` and ``` UNIQUE ``` constraints are created

## Query Optimiser
- Analyses indexes to improve performance
- Reduce disk i/o and fewer system resources
