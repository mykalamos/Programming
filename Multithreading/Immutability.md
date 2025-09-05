
# Immutability
- Object once created cannot be modified

## Benefits
- Thread safe - no race conditions
- No locking
- Predictability - easier to debug, no thread freezing needed
- Pure functions - no side effect programming

## Records
- Immutable by default
- Built-in with expressions
- Value-based equality
- Deconstructor support

| Record Type              | Is Reference Type? | Supports `with`? | Value Equality? |
|--------------------------|--------------------|------------------|------------------|
| `record`                 | ✅ Yes              | ✅ Yes           | ✅ Yes         |
| `record class`           | ✅ Yes              | ✅ Yes           | ✅ Yes         |
| `record struct`          | ❌ No (value type)  | ✅ Yes (C# 10+)  | ✅ Yes         |
| `readonly record struct` | ❌ No (value type)  | ✅ Yes           | ✅ Yes         |

## Conclusion
- Trade performance for safety and simplicity
