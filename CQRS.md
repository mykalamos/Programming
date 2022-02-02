# Command and Query Responsibility Segregation
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
- Disadvantage - cant autogenerate via ORM
- Greater isolation => Separates read and write datastores
  - Materialised view of to avoid complex joins
  - Different store types
    - R = Document
    - W = Relational
    - Requires synchronisation - Write model publishes an event.
    - Write and publish must be a transaction
    - Multiple read stores for distributed scenarios
- Event Sourcing
  - App state stored as sequence of events
  - Current state is constructed by replay
  - Same events can be used to notify the read model

## Benefits
- Independent Scaling
- Optimsed data schema - appropriate for read and write
- Security - only entitled entities creating writes
- Separation of concerns
- Simpler queries - materialised views

# Implementation issues
- Increased complexity esp if with Event Sourcing
- Messaing 
- Eventual consistency - stale reads

# When to use
- Collaborative domains - many users accessing data in parallel
  - Minimise merge conflicts, command can resolve them
- Task based user interfaces
- Data reads require extra performance

# Event sourcing and CQRS
- Using a stream avoids conflicts and maximises performance and scalability
- Asynchronous build of read data
- Event stream definitive view of data
  - Materialised views can be regenerated
  - Read view is a durable, read-only cache
