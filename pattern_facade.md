
# Facade Pattern

## Usage

## Description
The Facade Pattern is a structural design pattern that provides a simplified interface 
to a complex system of classes, library, frameworks APIs etc. The main idea is to hide 
the complexity of the system and provide an easier way to access its functionalities. 
It involves creating a facade that wraps the complicated subsystems, thereby allowing 
clients to interact with the subsystem through a single unified interface.


Here is an example in the form of a class diagram:

``` mermaid
classDiagram
    class Facade {
        operation()
    }
    class SubsystemClassA {
        subOperationA()
    }
    class SubsystemClassB {
        subOperationB()
    }
    class SubsystemClassC {
        subOperationC()
    }
    Facade --> SubsystemClassA : Uses
    Facade --> SubsystemClassB : Uses
    Facade --> SubsystemClassC : Uses
    Client --> Facade : Uses
```

* The Facade class has a method called operation().
* The SubsystemClassA, SubsystemClassB, and SubsystemClassC classes each have their own methods.
* The Facade class uses (-->) the subsystem classes.
* The Client interacts with the Facade.
