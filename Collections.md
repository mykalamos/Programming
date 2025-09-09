# Collections

# 📚 Summary: Non-Dictionary / Non-Lookup Collection Types in .NET

| Collection Type            | Thread-Safe | Mutable | Ordered | Duplicate Items Allowed | Optimized For               | Typical Use Case                      | .NET Version            |
|----------------------------|-------------|---------|---------|-------------------------|----------------------------|-------------------------------------|-------------------------|
| `List<T>`                  | ❌ No       | ✅ Yes  | ✅ Yes  | ✅ Yes                  | Fast indexed access         | General-purpose dynamic array       | .NET 2.0+               |
| `LinkedList<T>`            | ❌ No       | ✅ Yes  | ✅ Yes  | ✅ Yes                  | Fast insert/remove anywhere | Doubly-linked list scenarios        | .NET 2.0+               |
| `HashSet<T>`               | ❌ No       | ✅ Yes  | ❌ No   | ❌ No                   | Fast membership tests       | Unique item collections              | .NET 3.5+               |
| `SortedSet<T>`             | ❌ No       | ✅ Yes  | ✅ Yes  | ❌ No                   | Sorted unique items         | Sorted unique collections            | .NET 3.5+               |
| `Queue<T>`                 | ❌ No       | ✅ Yes  | ✅ Yes  | ✅ Yes                  | FIFO access                | First-in-first-out processing       | .NET 2.0+               |
| `Stack<T>`                 | ❌ No       | ✅ Yes  | ✅ Yes  | ✅ Yes                  | LIFO access                | Last-in-first-out processing        | .NET 2.0+               |
| `ImmutableList<T>`         | ✅ Yes      | ❌ No   | ✅ Yes  | ✅ Yes                  | Immutable list operations   | Thread-safe functional programming  | .NET Core / Immutable   |
| `ImmutableHashSet<T>`      | ✅ Yes      | ❌ No   | ❌ No   | ❌ No                   | Immutable set operations    | Immutable unique collections         | .NET Core / Immutable   |
| `ImmutableQueue<T>`        | ✅ Yes      | ❌ No   | ✅ Yes  | ✅ Yes                  | Immutable FIFO queue        | Immutable queue usage                 | .NET Core / Immutable   |
| `ImmutableStack<T>`        | ✅ Yes      | ❌ No   | ✅ Yes  | ✅ Yes                  | Immutable LIFO stack        | Immutable stack usage                 | .NET Core / Immutable   |
| `ConcurrentQueue<T>`       | ✅ Yes      | ✅ Yes  | ✅ Yes  | ✅ Yes                  | Thread-safe FIFO queue      | High-performance concurrent FIFO     | .NET 4.0+               |
| `ConcurrentStack<T>`       | ✅ Yes      | ✅ Yes  | ✅ Yes  | ✅ Yes                  | Thread-safe LIFO stack      | High-performance concurrent LIFO     | .NET 4.0+               |
| `ConcurrentBag<T>`         | ✅ Yes      | ✅ Yes  | ❌ No   | ✅ Yes                  | Thread-safe unordered bag  | Fast concurrent unordered collections| .NET 4.0+               |
