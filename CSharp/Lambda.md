# Lambda
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions
- Anonymous function
- => operator
- 2 types
  - Expression
  - Statement ```{ ... }```
- Can be converted to delegate
- V7 Tuples supported
- Not used in query expressions directly
- Type inference in lambda
- Explicit return type supported

## Async
```
button1.Click += async (sender, e) => { await MethodAsync(); } 
```
## Standard Query Operators
```
numbers.Count(n => n % 2 == 1);
```
## Attributes
- V10
```
var inc = [return: Example(1)] (int s) => s++;
```
## Capture scope
- Lambdas can use outer variables
  - Stored in lambda even if would otherwise go out of scope
