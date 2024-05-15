# Bridge Pattern

## Usage

## Description
The Bridge Pattern is a structural design pattern that aims to decouple an abstraction from its implementation. 
It allows you to split a large class or a set of closely related classes into two separate hierarchies: 
the abstraction and the implementation. These two hierarchies can evolve independently of each other.


Here is an example in the form of a class diagram:

``` mermaid
classDiagram
    class Abstraction {
        +operation()
    }
    class Implementor {
        +operationImp()
    }
    class Shape {
        -color: Implementor
        +draw()
    }
    class Circle {
        +draw()
    }
    class Square {
        +draw()
    }
    class Red {
        +applyColor()
    }
    class Blue {
        +applyColor()
    }

    Abstraction --> Shape : Uses
    Shape --> Implementor : Delegates
    Shape --> Circle
    Shape --> Square
    Implementor --> Red
    Implementor --> Blue

```

* Abstraction represents the high-level control layer (e.g., GUI).
* Implementor represents the underlying code (e.g., OS API).
* Shape delegates work to the Implementor.
* Circle and Square are specific shape classes.
* Red and Blue are color classes.
