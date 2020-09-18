---
description: What makes Java Java?
---

# Technical Details

## Object-oriented

Object-oriented programming, often shortened to OOP, is a term that is used to describe languages that support the concept of "objects" in programming. **Objects can represent real things or objects, as well as abstract things.** For example, an object can represent a car, an animal, an error, a color, clothing items, etc. Objects contain data, known as properties, and can perform methods.

There are 4 pillars, or rules, of OOP: 

1. [Inheritance](../advanced/java/inheritance-and-composition.md#inheritance), the sharing of information
2. [Abstraction](../advanced/java/abstract-classes-and-interfaces.md), the hiding of information
3. [Encapsulation](../basic-java/classes.md#instance-variables), the grouping of information
4. [Polymorphism](../advanced/java/abstract-classes-and-interfaces.md#polymorphism), the redefining of information

Moreover, there are 3 qualities that make a language a pure OOP language.

1. Pre-defined types are objects
2. User-defined types are objects
3. Methods must be called on objects

Java is considered an OOP language because it follows \(although not strictly\) these rules. These topics will be covered later in the advanced section. 

{% hint style="info" %}
Contrary to popular belief, Java is _not_ a _pure_ object-oriented language, which means that it does not completely abide by the 7 main concepts of OOP. We will learn why in the primitive data types lesson.
{% endhint %}

## Class-based

One of the defining characteristics of OOP languages are classes. **Objects are** _**instances**_ **of a class.** Think of a class as a blueprint for creating classes—for example, when you buy a LEGO® construction set, the blueprint for creating the model is like a class, and the final product is an object.

## Garbage-collected

In programming, there is a concept known as memory. The more memory your program uses, the slower it will run, and the less efficient it will be. Java, like many languages today, manages the memory your program uses automatically through use of a _garbage collector_. It collects the memory used by objects that are no longer being used by the program, and opens that memory back up to the program.

Generally, memory management isn't that much of a concern with a garbage collector, but if your program becomes very large or _memory-intensive_, you should consider what parts of your program is running slow and refactor \(rethink\) that code.

