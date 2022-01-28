# Nullable reference types

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
