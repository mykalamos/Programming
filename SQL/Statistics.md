https://docs.microsoft.com/en-us/sql/relational-databases/statistics/statistics?view=sql-server-ver15

- Query optimiser uses statistics to improve query performance.
  - Optimiser creates its own stats but somethines others are needed

- BLOBs - distribution of data in a table/indexed view
- QO estimates based on this
  - Cardinality: Number of rows in query
  - Helps to select Index seek rather than Index can

- Each stats object includes
  - a histogram of data distribution in first column
  - Multi-column - correlation of values between columns (densities)

## Histogram creation
- Sorts valuse
- Cmputes value count
- Aggregates to MAX(200) contiguous histogram steps
