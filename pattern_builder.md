# Builder Pattern

## Usage

## Description
The Builder Pattern is a creational design pattern that allows you to construct 
complex objects step by step. It’s particularly useful when creating objects with 
many attributes or configurations.


Here is an example in the form of a class diagram:

``` mermaid
classDiagram
    class Director {
        +construct(builder: Builder)
    }
    class Builder {
        +buildPartA()
        +buildPartB()
        +getResult(): Product
    }
    class ConcreteBuilderA {
        +buildPartA()
        +buildPartB()
        +getResult(): Product
    }
    class ConcreteBuilderB {
        +buildPartA()
        +buildPartB()
        +getResult(): Product
    }
    class Product {
        -partA
        -partB
        +assemble()
    }

    Director --> Builder : Uses
    Director --> ConcreteBuilderA : Uses
    Director --> ConcreteBuilderB : Uses
    ConcreteBuilderA --> Product : Creates
    ConcreteBuilderB --> Product : Creates

```

* Director coordinates the building process.
* Builder defines the construction steps.
* ConcreteBuilderA and ConcreteBuilderB implement the builder interface.
* Product represents the final complex object.
