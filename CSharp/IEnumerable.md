To be used in a foreach construct a type must

- Implement the ```IEnumerable``` interface which exposes the following member

```IEnumerator GetEnumerator()```

### IEnumerator members
1. ```bool MoveNext()```
1. ```object Current {get;}```
1. ```void Reset()```

- Enumerator remains valid unless elements are added, modified, or deleted.
- Next call to MoveNext or Reset throws an InvalidOperationException. 
- Access to collection is non-exclusive and therefore intrinsically not a thread-safe
procedure.

In .NET 2: interface IEnumerator<T> : IDisposable, IEnumerator

IList implements ICollection
----------------------------
- IsFixedSize
- IsReadOnly
- Item

- Add
- Clear
- Contains
- IndexOf
- Insert - Inserts an item to the IList at the specified index.
- Remove
- RemoveAt - Removes the IList item at the specified index.
