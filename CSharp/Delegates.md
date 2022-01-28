# Delegates
https://docs.microsoft.com/en-us/dotnet/csharp/delegates-overview
- Provide late binding
- ```delegate``` - below are not themselves delegates and cant be inherited
  - ```Delegate```
  - ```MulticastDelegate``` - what is compiled when keyword is used
## Declaration
```
public delegate bool IsNew(string key);
```
- Declaration of a new type not a variable
- Compiler generates handler
  - add
  - remove
## Create instance
 ```
public IsNew isNew;
```
## Invocation
- As a method
``` bool n = isNew("MyKey"); ```
- No guarantee a target has been added to delegate

# Auto-methods
- ```BeginInvoke()```
- ```EndInvoke()```
- ```Invoke```

# Generics
- ```Action``` - void return type
- ```Func``` - final param out ie output
- ```Predicate``` - ``` public delegate bool Predicate<in T>(T obj) ```
