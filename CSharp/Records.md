# Records
https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/tutorials/records
- V9 (record structs V10)
- Ideal for when data storage fundamental goal of type
- Value based equality
- Implicitly reference type
- Out of the box methods
  - ```Equals(object,Type)```
  - ```GetHashCode```
  - ```IEquatable<T>```
  -  ```operator==``` ```operator!=```
  -  ```ToString```

## Positional Records
- More concise e.g. ```public record X(string Field1, int Field2);```
- Generates
  - Constructor with params
  - Public properties. Init only for 
    - record class
    - readonly record struct
  - ```Deconstruct``` - value extraction

## Non-destructive mutation
```
var c = x with {Field1 = "a"};
```
