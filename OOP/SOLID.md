# SOLID Principles
https://blog.cleancoder.com/uncle-bob/2020/10/18/Solid-Relevance.html

> The best way to make a complicated mess is to tell everyone to “just be simple” and give them no further guidance.

## (S)ingle Responsibility
- *Gather together the things that change for the same reasons.*
- *Separate things that change for different reasons.*
- This will inevitably lead to smaller classes with few public methods.

## (O)pen-Closed
- *A Module should be open for extension but closed for modification.*

## (L)iskov Substitution
- *A program that uses an interface must not be confused by an implementation of that interface.*
```
Let Φ(x) be a property provable about objects x of type T.
Then Φ(y) should be true for objects y of type S where S is a subtype of T.
```
- This is not about inheritance. All implementations of intefaces are sub-types

## (I)nterface Segregation
- *Keep interfaces small so that users don’t end up depending on things they don’t need.*
- throw new NotImplementedException() - !

## (D)ependency Inversion
- *Depend in the direction of abstraction. High level modules should not depend upon low level details.*
- The general should not depend on the particular

