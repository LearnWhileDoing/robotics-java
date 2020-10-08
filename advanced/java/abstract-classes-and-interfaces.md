---
description: Hierarchical representation of information
---

# Interfaces and abstract classes

A key concept of OOP is _abstraction_, which is referred to as the hiding of information. However, to the average programmer, this definition doesn't help to explain what abstraction can really help you with. Let's dig deeper into what abstraction is and how it can help programmers develop their programs quicker.

Take this _schema_ \(a model of information\) of an `Animal`:

```text
Animal {
    string name;
    string species;
    string makeSound();
    void feed(int amount);
}
```

This is written in pseudo-code, not in any specific language, simply to get the point across. We can see that an `Animal` has a `name`, a `species`, it can `makeNoise` , and is able to be fed.

As we learned previously, objects can represent things, both tangible and intangible. We can instantiate a class to make a new object. But one could argue this doesn't directly apply to an `Animal` class: can you really just have an _animal_ as an object? Or must it be the specific species of the animal, like a _dog_ or a _cat_ that is really the object?

We can represent these types of dilemmas in Java. Say you have a schema that you want to represent specific information, but you don't want to be able to create an object of it. You want the schema to be required to be [`extended`](inheritance-and-composition.md#sub-classes) by some other class. How would a programmer accomplish this?

## Interfaces

An interface is very similar to a class, except it doesn't have any implementation, or definition of any methods or variables. You can _declare_ variables and methods, but you cannot specify how they are to be implemented. Take the following example:

```java
interface Animal {
    String name;
    String species;
    void makeNoise();
    void feed(int amount);
}
```

As you can see, while we declared the type and name of the instance variables and the return type and parameters of the methods, we did not actually implement them. Interfaces cannot be instantiated, only implemented.

 We can now create a `Dog` class that implements the `Animal` interface schema.

```java
class Dog implements Animal {
    String name;
    String species;
    
    private int hunger;
    
    public Dog(String theName) {
        name = theName;
        species = "Dog";
        hunger = 100;
    }
    
    void makeNoise() {
        return "woof!";
    }
    
    void feed(int amount) {
        hunger -= 100;
    }
}
```

The `Dog` class `implements` the `Animal` interface. Notice how when extending classes, you use the `extends` keyword, but when implementing an interface schema,  you use the `implements` keyword.

When implementing an interface, you must follow the schema defined by that interface. However, you are free to add more methods and instance variables as you please.

{% hint style="info" %}
All methods and instance variables defined by an interface and abstract class _must_ be [`protected`](inheritance-and-composition.md#protected). This is because interfaces enforce a strict inheritance policy. Other methods and instance variables do not have to be protected.
{% endhint %}

## Abstract Class

We know how to define a schema with no implementation. However, sometimes we need to have minimal implementation in our schemas because all the classes that implement it should behave in the described way. We can accomplish this using _abstract classes_.

Let's make a slightly more complex `Car` class.

```java
abstract class Car {
    String make;
    String model;
    String color;
    int year;
    
    abstract void accelerate();
    abstract void brake();
    
    void drive() {
        System.out.println("vroom vroom");
    }
}
```

Before we declared the `Car` class, we used the `abstract` class. This tells Java that this class is _abstract_, and cannot be instantiated. We also use the `abstract` keyword before any methods we don't implement. Now, we can make another class that _extends_ the `Car` class.

```java
class HondaCivic extends Car {
    double speed;
    
    public Car(String theColor) {
        color = theColor;
    }
    
    void accelerate() {
        speed += 0.5;
    }
    void brake() {
        speed -= 0.5;
    }
}
```

Unlike when implementing an interface, **you** _**do not**_ **have to redefine the fields of an abstract class**, you only have to implement the methods. In the `HondaCivic` class, the accelerate/brake adjusts the speed by +/-0.5. When a `HondaCivic` `drive()`s,  it will print out "vroom vroom" to the console because that method was already implemented.

### Polymorphism

When classes, we can _override_ the methods previously implemented. For example, many sports-cars make a different sound when they drive. We can represent this by overriding the `drive` method of the `Car` class.

```java
class Corvette extends Car {
    double speed;
    
    public Car(String theColor) {
        color = theColor;
    }
    
    void accelerate() {
        speed += 2.5;
    }
    void brake() {
        speed -= 2.5;
    }
    
    void drive() {
        System.out.println("rrrRRRRRrrrrrr");
    }
}
```

Now, your `Corvette` will sound much more ferocious than your `HondaCivic`.

This concept is known as _polymorphism_, the redefining of information. A parent class can act in different ways depending on its methods are redefined in its subclasses. 

{% hint style="info" %}
Use interfaces when you don't need to implement any methods, and vice versa.
{% endhint %}

