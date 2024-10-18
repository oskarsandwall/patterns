# List of Design Patterns

| Pattern | Description |
|---|---|
| [Adapter&nbsp;Pattern](pattern_adapter.md) | Allows incompatible interfaces to work together. It involves a single class that joins functionalities of independent or incompatible.<br/>[Solution Architecture], [Transformation], [Integration] |
| [Bridge&nbsp;Pattern](pattern_bridge.md) | Separates an object’s abstraction from its implementation so that the two can vary independently. |
| [Facade&nbsp;Pattern](pattern_facade.md) | Provides a simplified interface to a complex subsystem.<br/> [Solution Architecture], [Transformation], [Integration] |
| [Strangler&nbsp;Pattern](pattern_strangler.md) | [Solution Architecture], [Transformation] |
| [Publisher/Subscriber&nbsp;Pattern](pattern_pubsub.md) | [Solution Architecture], [Event-Driven], [Distributed] |
| [Event&nbsp;Streaming&nbsp;Pattern](pattern_eventstreaming.md) | [Solution Architecture], [Event-Driven], [Distributed] |
| [Event&nbsp;Sourcing&nbsp;Pattern](pattern_eventsourcing.md) | [Solution Architecture], [Event-Driven], [Distributed] |
| [Builder&nbsp;Pattern](pattern_builder.md) | Separates the construction of a complex object from its representation, allowing the same construction process to create various representations. |

## Patterns to be added
* [API Gateway](pattern_apigateway.md): Provides a unified interface to a set of microservices, simplifying client-side interactions. [Microservices]
* [Backends for Frontends (BFF)](pattern_backendsforfrontends.md): Create separate backend services for each frontend application or interface. Particulary useful when different frontends have unique requirements and need tailored backend services for optimal performance and/or user experience [Microservices]
* [Bulkhead](pattern_bulkhead.md): A resilience strategy used to isolate different parts of a system to prevent failures from cascading. [Microservices]
* Chain of Responsibility Pattern: Passes a request along a chain of handlers. Upon receiving a request, each handler decides either to process the request or to pass it to the next handler in the chain.
* Command Pattern: Encapsulates a request as an object, thereby allowing for parameterization of clients with queues, requests, and operations.
* Composite Pattern: Composes objects into tree structures to represent part-whole hierarchies. It lets clients treat individual objects and compositions uniformly.
* Decorator Pattern: Adds new functionalities to an object dynamically without altering its structure. This type of design pattern comes under structural pattern as this pattern acts as a wrapper to existing class.
* Facade Pattern: Provides a simplified interface to a complex subsystem.
* Factory Method Pattern: Defines an interface for creating an object, but lets subclasses alter the type of objects that will be created.
  * Abstract Factory Pattern: Allows the creation of families of related or dependent objects without specifying their concrete classes.
* Flyweight Pattern: Minimizes memory usage by sharing as much data as possible with other similar objects.
* Interpreter Pattern: Provides a way to evaluate language grammar or expression for a given language.
* Iterator Pattern: Provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.
* Mediator Pattern: Defines an object that encapsulates how a set of objects interact, promoting loose coupling by keeping objects from referring to each other explicitly.
* Memento Pattern: Captures and externalizes an object’s internal state so that the object can be restored to this state later.
* Observer Pattern: Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated * Prototype Pattern: Creates new objects by copying an existing object, known as the prototype.
* Proxy Pattern: Provides a placeholder for another object to control access, reduce cost, and reduce complexity.
* Singleton Pattern: Ensures a class has only one instance and provides a global point of access to it.interfaces.
automatically.
* State Pattern: Allows an object to alter its behavior when its internal state changes. The object will appear to change its class.
* Strategy Pattern: Defines a family of algorithms, encapsulates each one, and makes them interchangeable. Strategy lets the algorithm vary independently from clients that use it.
* Template Method Pattern: Defines the skeleton of an algorithm in an operation, deferring some steps to subclasses. Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure.
* Visitor Pattern: Represents an operation to be performed on the elements of an object structure. Visitor lets you define a new operation without changing the classes of the elements on which it operates.
