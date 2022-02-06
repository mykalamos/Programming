# Weak References
https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/weak-references

- GC cannot collect object while code can reach that object
- Strong reference

- A weak reference (WR) permits
- the GC to collect the object
- the application to access the object

- WR is valid only during the indeterminate amount of time until the object is collected when no strong references exist
- When using WR, the app can still obtain a strong reference to the object, which prevents it from being collected.
- Risk that GC will get to the object first before a strong reference is reestablished.

- WR are useful for objects that
  - use a lot of memory
  - easily recreatable
TODO
Suppose a tree view in a Windows Forms application displays a complex hierarchical choice of options to the user. If the underlying data is large, keeping the tree in memory is inefficient when the user is involved with something else in the application.

When the user switches away to another part of the application, you can use the WeakReference class to create a weak reference to the tree and destroy all strong references. When the user switches back to the tree, the application attempts to obtain a strong reference to the tree and, if successful, avoids reconstructing the tree.

To establish a weak reference with an object, you create a WeakReference using the instance of the object to be tracked. For a code example, see WeakReference in the class library.
