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

e.g. a tree view in a Windows Forms
- User switches to another part of the app, use WR to create a weak reference to the tree and destroy all strong references.
- When user switches back to tree, the application attempts to obtain a strong reference to the tree and, if successful, avoids reconstructing the tree.

## Short and Long Weak References
### Short
- The target of a short WR becomes ```null``` when the object is GC-ed.
- WR = managed object => subject to GC
- A short WR is the parameterless constructor for WeakReference.

### Long
- A long WR is retained after the object's ```Finalize``` method is called.
- This allows the object to be recreated, but the state of the object remains unpredictable.
- To use a long reference, specify ```true``` in the ```WeakReference``` constructor.
- If no ```Finalize``` method, the short WR functionality applies
- WR is valid only until the target is collected, which can occur anytime after the finalizer is run

- To establish a strong reference and use the object again, cast the ```Target``` property of a ```WeakReference``` to the type of the object.
- If the ```Target``` property returns ```null```, the object was collected

## Guidelines for Using Weak References

- Use long WR only when necessary as the state of the object is unpredictable after finalization
- Avoid using WRs to small objects because the pointer itself may be as large or larger
- Avoid using WRs as an automatic solution to memory management problems
  - Develop an effective caching policy for handling your application's objects.
