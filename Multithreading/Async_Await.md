# Task Asynchronous Programming model (TAP)
- Code as sequence of statements
- But executes based on 
  -  External resource allocation
  -  When task(s) finish

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

- Task = a unit of work with a promise return results in the future.
- The result of the operation is self-sufficient and is a first-class citizen.
