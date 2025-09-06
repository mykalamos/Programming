# Generics
- Code that can work with a range of data types without sacrificing type-safety.

## Pre-generics
```csharp
    object o = "hello";
```
- No compile time checking
- Casting needed
- Runtime error risk

## With Generics
```csharp
public class Box<T>
{
    public T Value;
}
```
- Type safety
- No casting
- Performant for value types (no boxing/unboxing)
- Reusability

## Scope
- Class
- Interface
- Struct
- Method
- Delegate

## Type Constraints

| C# Version | Constraint Syntax           | Description                                                        |
|------------|-----------------------------|--------------------------------------------------------------------|
| C# 2.0     | `where T : class`           | `T` must be a reference type                                       |
| C# 2.0     | `where T : struct`          | `T` must be a value type (non-nullable)                           |
| C# 2.0     | `where T : new()`           | `T` must have a parameterless constructor                          |
| C# 2.0     | `where T : BaseClass`       | `T` must inherit from the specified base class                    |
| C# 2.0     | `where T : IInterface`      | `T` must implement the specified interface                        |
| C# 2.0     | `where T : U`               | `T` must be or derive from type parameter `U`                     |
| C# 7.3     | `where T : unmanaged`       | `T` must be an unmanaged type (no references, only primitive fields) |
| C# 8.0     | `where T : notnull`         | `T` must be non-nullable (applies to both ref and value types)    |
| C# 11.0    | `static abstract` members   | Enables static polymorphism (e.g., generic math operators in interfaces) |
| C# 11.0    | `where T : INumber<T>`      | `T` must implement the numeric interface for generic math         |

# Open vs Closed

| Aspect                 | Open Generic Types                              | Closed Generic Types                                       |
|------------------------|------------------------------------------------|------------------------------------------------------------|
| **Definition**          | Generic type with unspecified parameters (e.g., `List<T>`) | Generic type with specific type arguments (e.g., `List<int>`) |
| **Metadata**            | Stores generic definition with type parameters intact | Stores constructed type with concrete type arguments substituted |
| **Instantiation**       | Cannot be directly instantiated; serves as a blueprint | Can be instantiated with concrete types at runtime          |
| **JIT Compilation**     | No machine code generated directly; only metadata | Machine code generated or reused specialized for concrete types |
| **Code Sharing**        | N/A — no executable code yet                    | Shared for reference types; unique per value type           |
| **Usage Examples**      | `typeof(List<>)`, reflection, generic declarations | `new List<int>()`, `List<string>`                           |
| **Runtime Type Object** | Represents generic type definition               | Represents constructed type with actual type arguments      |
| **Performance**         | No direct JIT code, only metadata               | JIT code generated on first use, optimized per type         |
| **Reflection**          | Can inspect generic parameters and constraints | Can inspect actual type arguments and constructed members   |

