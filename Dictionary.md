# Dictionary
- `Dictionary<TKey, TValue>` 
    - a hash table-based data structure
    - maps unique keys to values.

## Keys: `GetHashCode()` / `Equals()` Contract

- `GetHashCode()` !=> the same value for equal keys.
- `Equals()` !=> `true` when two keys are considered equal.

- If overriding one then override other
- Avoid mutable keys

## Resizing and Rehashing

### Growth
- The bucket array is resized to a larger capacity (usually a prime number) typically around 0.72 to 0.75 load factor
- All existing entries are rehashed into the new buckets.
### Why?
- Maintain O(1) average-case performance.
- Avoid high load factors and excessive collisions.

- Load Factor = (Number of entries) / (Number of buckets)

## Implementations
# 📘 Summary: Dictionary & Lookup Types in C#/.NET

| Type | Thread-Safe | Mutable | Key Uniqueness | Value Mapping | Optimized For | Use Case | .NET Version |
|------|-------------|---------|----------------|----------------|----------------|----------|---------------|
| `Dictionary<TKey, TValue>` | ❌ No | ✅ Yes | ✅ Unique keys | One value per key | Fast lookups | General-purpose hash table | .NET 2.0+ |
| `ConcurrentDictionary<TKey, TValue>` | ✅ Yes | ✅ Yes | ✅ Unique keys | One value per key | Thread-safe access | Multi-threaded scenarios | .NET 4.0+ |
| `SortedDictionary<TKey, TValue>` | ❌ No | ✅ Yes | ✅ Unique keys | One value per key | Sorted keys | Ordered key-value pairs | .NET 2.0+ |
| `ImmutableDictionary<TKey, TValue>` | ✅ Yes | ❌ No | ✅ Unique keys | One value per key | Functional immutability | Shared config, functional code | .NET Core 1.0+ |
| `ReadOnlyDictionary<TKey, TValue>` | ✅ (if source is) | ❌ No | ✅ Unique keys | One value per key | API surface restriction | Expose read-only views | .NET 4.5+ |
| `FrozenDictionary<TKey, TValue>` | ✅ Yes | ❌ No | ✅ Unique keys | One value per key | Preprocessed hash table | Cold, read-heavy workloads | .NET 8.0+ |
| `ILookup<TKey, TElement>` | ✅ Yes | ❌ No | ✅ Unique keys | ✅ Multiple values per key | Grouped lookups | Grouping and querying | .NET 3.5+ (LINQ) |
| `Lookup<TKey, TElement>` | ✅ Yes | ❌ No | ✅ Unique keys | ✅ Multiple values per key | Built via LINQ | Result of `ToLookup()` | .NET 3.5+ |
