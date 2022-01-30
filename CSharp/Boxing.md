# Un/Boxing
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing
## Boxing
- Converting value type to
  1. ```object```
  2. any interface it implements
- Stored on heap
- Implciit ``` object o = 2;```
## Unboxing
- Extraction of value type
- Explicit ``` int i = (int)o;```

## Performance
- Un/Boxing computationally expensive processes.
- In boxing a new object must be allocated and constructed.
- Cast required for unboxing is also expensive computationally but less so
