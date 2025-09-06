# Functional Core Imperative Shell

## Functional Core
- Pure functions
- No side effects
- Deterministic
- Easy to test
- No dependencies (no file system, DB, time, random, etc.)

## Imperative Shell
- Handles I/O (files, DB, HTTP, console, caching, middleware, etc.)
- Deals with side effects
- Orchestrates execution flow
- Usually small and thin
- TODO - pipelining

``` pgsql
Application
│
├── Imperative Shell
│   ├── Controllers / CLI / UI
│   ├── Infrastructure (HTTP, DB, Logging)
│   └── Services (use cases, orchestration)
│
└── Functional Core
    ├── Domain models
    ├── Business logic (pure functions)
    └── Validation, Calculations, Rules
```

## 🆚 Imperative vs Functional Programming

| Feature                    | Imperative Programming                                | Functional Programming                              |
|----------------------------|--------------------------------------------------------|-----------------------------------------------------|
| **Core idea**              | Code is a sequence of statements that change state     | Code is a composition of pure functions             |
| **Focus**                  | *How* to perform operations (step-by-step)             | *What* result you want                              |
| **State**                  | Mutable state is common                                | State is immutable                                  |
| **Functions**              | Procedures with possible side effects                  | Pure functions with no side effects                 |
| **Control flow**           | Loops, conditionals                                    | Recursion, higher-order functions                   |
| **Side effects**           | Expected and common (e.g., I/O, mutation)              | Avoided in the core logic                           |
| **Testing**                | Requires mocking/stubbing for side effects             | Easier to test pure functions                       |
| **Reusability**            | Harder to reuse due to side effects                    | Functions are highly reusable                       |
| **Debuggability**          | Can be harder due to hidden state changes              | Easier due to determinism                           |
| **Examples in C#**         | `foreach`, `if`, `Console.WriteLine`, mutable objects  | `Select`, `Where`, LINQ, pure functions             |
