[< Back to the list of patterns](patterns_list.md)

# Strategy Pattern

## Usage
In simple terms: Strategy lets you swap “how something is done” at runtime without changing the code that asks for it to be done.

## Description
The Strategy pattern is a behavioral design pattern that lets you define a family of algorithms, encapsulate each one, and make them interchangeable. 
It allows the algorithm to vary independently from the code that uses it.
The pattern also aligns very well with [SOLID](https://en.wikipedia.org/wiki/SOLID) principles which is commonly used in software development.

### UML-style Class diagram
``` mermaid
classDiagram
    class Context {
        -strategy : Strategy
        +Context(strategy : Strategy)
        +SetStrategy(strategy : Strategy) void
        +Execute() void
    }

    class Strategy {
        <<interface>>
        +Execute() void
    }

    class ConcreteStrategyA {
        +Execute() void
    }

    class ConcreteStrategyB {
        +Execute() void
    }

    Context --> Strategy : uses
    Strategy <|.. ConcreteStrategyA
    Strategy <|.. ConcreteStrategyB
```

### Sequence diagram - choosing and using a strategy
``` mermaid
sequenceDiagram
    actor Client
    participant Context
    participant StrategyA as ConcreteStrategyA
    participant StrategyB as ConcreteStrategyB

    Client->>StrategyA: create()
    Client->>Context: new Context(StrategyA)
    Client->>Context: Execute()
    Context->>StrategyA: Execute()

    Note over Client,Context: Later, client switches strategy

    Client->>StrategyB: create()
    Client->>Context: SetStrategy(StrategyB)
    Client->>Context: Execute()
    Context->>StrategyB: Execute()
```

## Key features
1. **Encapsulated algorithms:** Each variant of an algorithm is its own class implementing a common interface.
2. **Interchangable behaviors:** Strategies share the same interface, so the client/context can swap them without changing its own code.
3. **Context delegates to strategy:** The context doesn’t implement the algorithm; it delegates to the selected strategy.
4. **Run-time selection of behavior:** The specific strategy can be chosen at runtime (via configuration, user input, or DI - Dependency Injection).
5. **Eliminates conditionals for behavior selection:** Replaces big if/else or switch blocks with polymorphism.
6. **Supports Open/Closed Principle:** New behaviors are added by creating new strategy classes; existing code stays unchanged.

## Benefits
1. **Cleaner, more maintainable code:** Logic for each variation is isolated in its own class, making it easier to read and modify.
2. **Easier to add new behaviors:** Adding a new algorithm typically doesn’t require touching the context or other strategies.
3. **Improved testability:** Each strategy can be unit-tested in isolation; the context can be tested with mock or stub strategies.
4. **Greater flexibility:** You can dynamically change behavior (e.g., different discount rules, sorting methods, validation rules).
5. **Better adherene to SOLID:** Respects the Single Responsibility Principle (each strategy has one reason to change) and Open/Closed Principle.
6. **Promotes reuse:** Strategies can be reused across different contexts that need the same kind of behavior.
7. **Supports configuration and DI:** Works well with dependency injection containers to select strategies via configuration, feature flags, or environment.

[< Back to the list of patterns](patterns_list.md)
