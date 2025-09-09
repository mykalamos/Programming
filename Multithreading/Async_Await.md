# Task Asynchronous Programming model (TAP)
- Code as sequence of statements
- But executes based on 
  -  External resource allocation
  -  When task(s) finish

  ## TL;DR
 Syntax sugar to write asynchronous, non-blocking code in a way that looks synchronous.

## Await
- Non blocking way to start asynchronous action in a synchronous fashion
- Containing method must be marked ```async```

## Exceptions
- ```Task.Exception``` Property = ```AggregateException```

## Efficient await
- ``` Task.WaitAll```
- ``` Task.WhenAny```

## Implementation
https://devblogs.microsoft.com/premier-developer/dissecting-the-async-methods-in-c/

- Task = a unit of work with a promise to return results in the future.
- The result of the operation is self-sufficient and is a first-class citizen.
- State machine lives on heap so can be restarted on a different thread
- Stack is saved in machine - as a class


A single async method call becomes
  - one state machine
  - multiple internal states if the method contains multiple await statements.

- One method call = one state machine
- Multiple awaits inside that method = multiple states in that machine

# Performance
TODO