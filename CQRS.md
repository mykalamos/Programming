# Command and Query Reponsibility Segregation
https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs
- Separates for a data store
  - Read
  - Update
- Can maximise
  - Performance
  - Scalability
  - Security
- Prevents updates from causing domain level conflicts

## Context and Problem
- Same model for Updates/Reads
- Works well for CRUD
- More complex scenarios
  - Read (R) - multiple queries, dtos with different shapes
  - Write (W) - business and validation logic
- R/W often asymetrical.
  - Different requirements for
    - Performance
    - Scale
  - Mismatch between R/W representations of data
  - Data contention
  - Performance - complexity of read queries
  - Security - R/W - exposing data in wrong context

## Solution
- Commands
  - Update data
  - Task based rather than data centric
  - Can be asynchronous
- Queries
  - Read data
  - Never modify
  - DTO contains no business logic
- Disadvantage 

