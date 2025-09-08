# Closures

- A function that "remember" the variables from the scope in which it was created, even after that scope has finished executing.

``` csharp
Func<int> GetCounter()
{
    int count = 0;

    return () =>
    {
        count++;
        return count;
    };
}
```
- Even though the method `GetCounter()` returns and ends, the variable `count` persists because it's captured by the returned lambda.

# Pitfalls
## Loops

``` csharp
var actions = new List<Action>();

for (int i = 0; i < 3; i++)
{
    actions.Add(() => Console.WriteLine(i));
}

foreach (var action in actions)
{
    action(); // Prints 3, 3, 3
}

```

## Scenarios
| Scenario              | Description                                           |
|-----------------------|-------------------------------------------------------|
| LINQ queries          | Capturing variables in `Where`, `Select`, etc.       |
| Event handlers        | Capturing local state in event listeners             |
| Async operations      | Maintaining context in async callbacks               |
| Stateful delegates    | Returning functions with internal state              |


## Summary

- A closure is a function that captures variables from its surrounding scope.
- C# handles closures by promoting captured variables to a hidden class -> Heap allocation

- Be cautious with closures in loops — use a temporary variable when needed.