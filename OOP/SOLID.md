# SOLID Principles
https://blog.cleancoder.com/uncle-bob/2020/10/18/Solid-Relevance.html

## (S)ingle Responsibility
- *Gather together the things that change for the same reasons.*
- *Separate things that change for different reasons.*

## (O)pen-Closed
- *A Module should be open for extension but closed for modification.*

## (L)iskov Substitution
- *A program that uses an interface must not be confused by an implementation of that interface.*
```
Let Φ(x) be a property provable about objects x of type T.
Then Φ(y) should be true for objects y of type S where S is a subtype of T.
```

## (I)nterface Segregation
- *Keep interfaces small so that users don’t end up depending on things they don’t need.*

## (D)ependency Inversion
- *Depend in the direction of abstraction. High level modules should not depend upon low level details.*
