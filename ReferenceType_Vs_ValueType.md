# Reference Type vs Value Type

| Reference Type | Value Type |
| --- | --- |
| Allocated on managed heap| On thread's stack |
| Lifetime managed by garbage collector | Reclaimed outside of defining scope |
| Inherits from System.Object| Also System.ValueType |
| Can be inherited if not sealed | Inherently sealed |
| Can inherit from other RT | Cannot explicitly inherit |
| Can override finalize | Cannot |
| Can define parameterless constructor | Cannot |
| Can have field initialisers | Cannot |
