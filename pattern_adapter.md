# Adapter Pattern

## Usage

## Description
The Adapter Pattern is a structural design pattern that allows objects with incompatible
interfaces to collaborate. It acts as a bridge between two incompatible interfaces, 
enabling them to work together seamlessly. Where the [Facade pattern](pattern_facade.md) 
simply hides the complexity of what is behind it, the adapter pattern actually transform
the informations information.


Here is an example in the form of a class diagram:

``` mermaid
classDiagram
    class ExistingObject {
        +existingMethod()
    }
    class Adapter {
        -wrappedObject: ExistingObject
        +adapterMethod()
    }
    class NewObject {
        +newMethod()
    }

    ExistingObject --> Adapter : Uses
    Adapter --> NewObject : Adapts
```

* ExistingObject represents the class with an incompatible interface.
* Adapter is the adapter class that wraps the ExistingObject.
* NewObject is the class with the expected interface.
* The adapter’s adapterMethod() translates calls to existingMethod() and delegates them to newMethod().
