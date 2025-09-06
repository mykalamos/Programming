# LINQ
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/
- Query capability integrated directly into C# language
- A consistent query experience for
  1. objects (LINQ to Objects)
  2. relational databases (LINQ to SQL)
  3. XML (LINQ to XML)
- Syntaxes
  1. Query
  2. Method

# Select vs SelectMany
| Operator | Step 1 | Step 2 | Step 3 |
| --- | --- | --- | --- |
| `Select` | For each item | apply the selector | return one output per input. |
| `SelectMany` | For each item | apply the selector that returns sequence | Flatten all sequences into one |

`SelectMany`, `GroupBy` operate on collections within collections.