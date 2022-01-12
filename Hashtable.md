# Hashtables

- Hashtables are associative arrays that index using an arbitrary object as opposed to an ordinal index.
- Asymptotic access time is O(1).

## GetHashCode contract
1. Value returned must be constant for a given instance of a type.
2. Two equal objects must return the same hashcode.

Returning the same hashcode for non-equal objects is not a violation but does cause bunching.

- Objects inheriting from ValueType are boxed in a hashtable so modification operations to dependent variables will not affect the contract.
- Default implementation for System.Object does not use member data but System.ValueType does.

## Solutions for reference types

1. Base algorithm on constant or read-only data.
2. Make type immutable.

System.Drawing.Point namespace returns the XOR of its x and y member variables.

Hashtable's algorithm is:
```
H(key) = [GetHash(key) + 1 + (((GetHash(key) >> 5) + 1) % (hashsize - 1))] % hashsize
```

## Collision Resolution in the Hashtable Class

In the event of collisions a secondary hashing function is used (rehashing,
double hashing).
```
Hk(key) = [GetHash(key) + k + (((GetHash(key) >> 5) + 1) % (hashsize - 1))] % hashsize
```

## Load Factors

- The maximum ratio of items in the Hashtable to the total number of slot.
- Specifiable range is 0.1 and 1.0 (1.0 is scaled down to 0.72 which is considered optimal by Microsoft).

On addition, if the load factor is to be exceeded expansion occurs.
