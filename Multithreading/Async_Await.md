# Task Asynchronous Programming model (TAP)
- Code as sequence of statements
- But executes based on 
  -  external resource allocation
  -  when task finish

## Await
- Non blocking way to start asynchronous action.
- Containing method must be marked ```async```

## Exceptions
- ```Task.Exception``` Property = ```AggregateException```


## Efficient await
- ``` Task.WaitAll``
- ``` Task.WhenAny``
