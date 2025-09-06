# Interfaces
https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/interface
- Defines contracts for classes, records, structs
    - Consts
    - Operators
    - Methods
    - Static Ctor
    - Nested tpes
    - Static fields, methods, properties
    - Member declarations
    - Explicit access modifiers (default `public`)

- Not allowed
    - Instance Fields
    - Auto-Implemented properties
    - Finalizers / Destructors

- V8 default implementation
- Static members also allowed (V11)
    - `static abstract`
    - `static virtual`

- Rationale for extending interfaces (instead of using abstract base class)
    - Generic constraints require interfaces
    - Struct cannot inherit
    - Multiple inheritance not allowed for class but
        - Multiple `interface` allowed 
    - Generic Math & Static Polymorphism (V11/net70)