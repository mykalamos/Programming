# Nullable reference types
https://docs.microsoft.com/en-us/dotnet/csharp/nullable-references
- V8
- Features to reduce runtime throwing ```NullReferenceException```
  - e.g. when dereferencing a variable whose value is ```null```

## Null state analysis
- Enabled by default in .NET 6 for new projects
- Emits warnings when code may dereference ```null```
- States
  - *not-null*
  - *maybe-null*
 - Compiler determines above as follows:
  - variable assigned to non-null value
  - variable checked against null and not modified since

## Attributes on API Signatures
- ```[NotNullWhen(false)] string message```
  - ```message``` ```not-null``` 

## Nullable variable annotations
- For member variables to help compiler in *null-state* analysis
- Same syntax as nullable value type e.g. ``` string? name ```
- Implicitly typed local varialbes (```var```) are nullable reference types
- Null forgiving - override compiler analysis - ```name!.Length ```

## Generics
- V9
- Different rules for value and reference types
- If T is string T? is string
- If T is value type T? also value type
- If T is string? T? also string?
- Constraints: class class? notnull
