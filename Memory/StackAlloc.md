# stackalloc
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/stackalloc

- Allocates a block of memory on the stack
- A stack allocated memory blockis automatically discarded when method returns
- Cannot explicitly free the memory
- Not subject to garbage collection
- Doesn't have to be pinned with ```fixed```

TODO
