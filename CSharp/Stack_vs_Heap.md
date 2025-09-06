# (Call) Stack
```
[ Return Address  ]
[ Saved Registers ]
[ Parameters      ]
[ Local Value a   ] ← Value type
[ Local Value p   ] ← Struct value type (inlined)
```

# Comparison
| Aspect                | Heap                                              | Stack                                             |
|-----------------------|--------------------------------------------------|---------------------------------------------------|
| **Purpose**           | Dynamic memory allocation for variable-sized, long-lived data | Manage function calls and local variables in LIFO order |
| **Memory Organization**| Large pool; chunks allocated/freed in any order | Contiguous block; strict push/pop behavior         |
| **Allocation/Deallocation** | Manual or automatic; unpredictable order          | Automatic and deterministic; tied to function calls |
| **Lifetime of Data**  | Data lives until explicitly freed or collected    | Data lives only during function execution          |
| **Access Speed**      | Generally slower due to complexity and fragmentation | Very fast; simple pointer adjustments              |
| **Typical Use Cases** | Objects, dynamic data structures, flexible lifetime variables | Local variables, function parameters, return addresses |

# Needs
- Stack - fast, predictable management of short-lived data (function calls). _Stack of plates - only the top can be added or removed_

- Heap - flexible, dynamic, and longer-lived data whose size or lifetime can’t be determined ahead of time. _Store room - boxes can be put anywhere, retrieved in any order, kept as long as you want_
