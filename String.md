# String

- Built in `reference type`
- Represents sequence of Unicode characters
- Immutable
- Reference type
    - Value type semantics
        - `==` compares contents
- Indexable
- Operator support `+`, `==`, `!=`
- Interned
``` csharp
    string a = "hello";
    string b = "hello";
    Console.WriteLine(object.ReferenceEquals(a, b)); // True — same memory reference
```

## Immutability benefits

| Benefit          | Description                                                                 |
|------------------|-----------------------------------------------------------------------------|
| **Thread Safety** | Immutable objects can be shared across threads without locks or race conditions. |
| **Predictability**| Once created, the object’s state doesn't change — making code easier to reason about. |
| **Security**      | Prevents accidental or malicious changes to sensitive values like passwords or file paths. |
| **Safe Hashing**  | Safe to use as keys in hash-based collections (`Dictionary`, `HashSet`) since their value won't change. |
| **String Interning** | The CLR can safely reuse identical string literals in memory.           |
| **No Side Effects**| Passing an immutable object to a method ensures it won’t be modified inside that method. |
| **Simpler Debugging** | Fewer unexpected changes = fewer bugs and easier stack traces.         |
| **Functional Style** | Immutability aligns with functional programming principles (pure functions, no side effects). |
