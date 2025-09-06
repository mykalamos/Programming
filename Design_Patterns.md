
https://w3sdesign.com/GoF_Design_Patterns_Reference0100.pdf

### Creational Patterns

| Pattern           | Description | C# Usage Example |
|------------------|-------------|------------------|
| **Singleton** | Ensures a class has only one instance and provides a global access point. | ```var logger1 = Singleton.Instance; ``` |
| **Factory Method** | Lets subclasses decide which class to instantiate. | ``` product = creator.FactoryMethod().Execute();``` |
| **Abstract Factory** | Creates families of related objects without specifying concrete classes. | ``` new Client(new LightThemeFactory()).RenderUI();``` |
| **Builder** | Separates object construction from its representation. | ``` new MealBuilder().WithDrink("Coffee").WithMainDish("Steak").Build();``` |
| **Prototype** | Creates new objects by cloning existing ones. | ``` var cloned = original.Clone();``` |

### Structural Patterns

| Pattern        | Description | C# Usage Example |
|----------------|-------------|------------------|
| **Adapter** | Adapts one interface to another. | `var adapter = new Adapter(oldObject);` |
| **Bridge** | Decouples abstraction from implementation. | `var view = new View(new DarkTheme());` |
| **Composite** | Treats individual and group objects uniformly. | `root.Add(child); root.Operation();` |
| **Decorator** | Adds behavior dynamically. | `var decorated = new LoggingDecorator(service);` |
| **Facade** | Simplifies access to a subsystem. | `var api = new Facade(); api.Start();` |
| **Flyweight** | Shares objects to save memory. | `var font = factory.GetFont("Arial");` |
| **Proxy** | Controls access to another object. | `var proxy = new Proxy(realService); proxy.Request();` |

### Behavioral Patterns

| Pattern | Description | C# Usage Example |
|---------|-------------|------------------|
| **Chain of Responsibility** | Passes request along chain of handlers. | `handler1.SetNext(handler2).Handle(request);` |
| **Command** | Encapsulates a request as an object. | `invoker.SetCommand(new SaveCommand()); invoker.Execute();` |
| **Interpreter** | Implements grammar for expressions. | `var expr = new Add(new Num(1), new Num(2)); expr.Interpret();` |
| **Iterator** | Sequentially access elements. | `foreach (var item in collection) { ... }` |
| **Mediator** | Coordinates communication. | `colleague.Send("Hi");` |
| **Memento** | Captures and restores state. | `caretaker.Save(originator.CreateMemento());` |
| **Observer** | Notifies dependents on state change. | `subject.Attach(observer); subject.Notify();` |
| **State** | Alters behavior when state changes. | `context.SetState(new ActiveState()); context.Request();` |
| **Strategy** | Selects algorithm at runtime. | `context.SetStrategy(new QuickSort()); context.Execute();` |
| **Template Method** | Defines steps of an algorithm. | `game.Play();` |
| **Visitor** | Adds new operations to objects. | `element.Accept(new Visitor()); // visitor.Visit();` |

==================
Previous
# Creational
TODO
# Structural
## Adapter
- Allows classes with incompatible interfaces to work together
- ```Adapter``` convert interface of ```Adaptee``` to ```Target``` required by client

## Bridge
- Decouple abstraction from implementation so 2 can vary independently

## Composite
- Objects into tree structures. nodes can be treated uniformly
- Children collection
  -  Leaf
  -  Composite (recursive)

## Decorator
- Specialisation of Adapter
- Adding of responsibilties dynamically at _runtime_
  - Subclassing is compile time
- Different decorators add responsibilities to an object
  - Recursive nesting - new decorators not required for _combinations_ of functionalities

## Facade
- Provide unified higher-level interface to a set of interfaces
- Aids loose coupling betweens systems

# Behavioural
TODO
