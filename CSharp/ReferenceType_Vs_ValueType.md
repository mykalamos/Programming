# Reference Type vs Value Type

| Reference Type | Value Type | Notes |
| --- | --- | --- |
| Allocated on managed heap| On thread's stack (except fields or stored in array) | |
| Lifetime managed by garbage collector | Reclaimed outside of defining scope | |
| Inherits from ```System.Object```| Also ```System.ValueType``` | |
| Can be inherited if not sealed | Inherently sealed | |
| Can inherit from other RT | Cannot explicitly inherit | |
| Can override finalize | Cannot | |
| Can define parameterless constructor | Cannot | guarantee that `default(T)` produces a zero-initialized struct |
| Can have field initialisers | Cannot | |
| Pointer passed to function | Value copied to stack frame | |


# Function call semantics
| Type           | Passing Mode | What is Passed                        | Can Modify Caller’s Variable? | Can Modify Underlying Object/Data? |
|----------------|--------------|----------------------------------------|-------------------------------|-------------------------------------|
| **Value Type** | By Value     | A **copy** of the value                | ❌ No                          | ✅ Only the local copy              |
| **Value Type** | By Ref       | A **reference to the value variable** | ✅ Yes                         | ✅ Modifies original data directly  |
| **Reference Type** | By Value     | A **copy of the reference** (pointer) | ❌ No                          | ✅ Modifies the object via the reference |
| **Reference Type** | By Ref       | A **reference to the reference variable** | ✅ Yes                         | ✅ Modifies object and/or reassigns caller's variable |


# Reference type passed by ref
| Step                  | Memory Address | Contents             | Description                              |
|-----------------------|----------------|----------------------|------------------------------------------|
| **After `a = new Obj()`** | `0x5000`       | `0x1000`             | Variable `a` stores address of object    |
|                       | `0x1000`       | Object data (Value=10) | Object on heap                            |
| **At method call**     | `obj` param    | `0x5000` (address of `a`) | Parameter `obj` points to variable `a`  |
| **Inside `MyFunc` before reassignment** | `0x5000`       | `0x1000`             | `a` still points to original object      |
|                       | `0x1000`       | Object data (Value=10) | Original object data                      |
| **Inside `MyFunc` after reassignment** | `0x2000`       | Object data (Value=42) | New object allocated                      |
|                       | `0x5000`       | `0x2000`             | `a` updated to point to new object       |
|                       | `0x1000`       | Object data (Value=10) | Old object still in memory (may be collected later) |
| **After method returns** | `0x5000`       | `0x2000`             | `a` points to new object                  |
|                       | `0x2000`       | Object data (Value=42) | New object data                           |

# Reference type (default)
| Step                  | Memory Address | Contents             | Description                              |
|-----------------------|----------------|----------------------|------------------------------------------|
| **After `a = new Obj()`** | `0x5000`       | `0x1000`             | Variable `a` stores address of object    |
|                       | `0x1000`       | Object data (Value=10) | Object on heap                            |
| **At method call**     | `param` (copy) | `0x1000`             | Parameter receives a copy of the reference (points to object at 0x1000) |
| **Inside method before reassignment** | `0x1000`       | Object data (Value=10) | Both `a` and `param` point to same object |
| **Inside method after reassignment** | `0x2000`       | Object data (Value=42) | New object allocated                      |
|                       | `param`        | `0x2000`             | Parameter updated to point to new object (only local copy changes) |
|                       | `0x5000`       | `0x1000`             | Original variable `a` unchanged           |
| **After method returns** | `0x5000`       | `0x1000`             | `a` still points to original object       |
|                       | `0x1000`       | Object data (Value=10) | Original object data                      |
|                       | `0x2000`       | Object data (Value=42) | New object created but not referenced by `a` |
