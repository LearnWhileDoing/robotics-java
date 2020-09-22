---
description: What's a Java program like?
---

# Program Structure

## Basic Java Program

Let's look at a basic Java program and break it down.

`MyProgram.java`

```java
public class MyProgram {
   public static void main(String[] args) {
      System.out.println("Hello World");
   }
}
```

This program will print "Hello World" to the console. In almost every Java program including this one, you will notice a few things.

### Filename

The filename of every file in a Java program must be the name of the **single** public [class](../basic-java/classes.md), [interface](../advanced/java/abstract-classes-and-interfaces.md#interfaces), or [enum](../advanced/coming-soon.md).

**There can only be one main public class, interface, or enum in a file.**

### Java Syntax

Notice how each block of code begins and ends with _curly braces_. Curly braces show Java what part of your program belongs with which block of code.

Also, each _code statement_ must end with a semicolon.

### Comments

When we write programs in any language, we want to be able to understand what specific parts of our code does. We can write _comments_ in our code to give ourselves and other people an idea of what this code does.

There are two ways of writing comments in Java:

```java
/**
 * multi-line comment
 */

// single line comment
```

Multi-line comments must start with `/*` and end with `*/`

### Classes

Our Java program starts with the following line: `public class MyProgram`. Java is considered to be an "object oriented language". What this means is that all code that will be run by our program must be inside of a class. Everything in Java revolves around objects and classes. Objects are an _instance_ of a class, and each object contains its own instance _state_.

We learn more about classes [in another lesson](../basic-java/classes.md).

### Methods

Methods, or functions, are a set of commands that are used perform specific actions. Within our class `MyProgram` we have a method titled `main`. This method contains a command that calls the method `println`. Methods help us to be able to reuse code, so that we can write it once and then call it again anywhere else in our code.

[Jump to our lesson on methods.](../basic-java/methods.md)

### Access Specifiers

In Java, not everything in one class or program is openly available to another. This is called _access specification_. A programmer can specify the access of their program and it's components by using `public` and `private`. _Public_ means that any other program can use this class, variable, or method; _private_ means that only this program can use this class, variable, or method. There is a third access specifier \(`protected`\) but we won't use it in this course.

Later, we will explain in more detail the importance of [access specification](http://localhost:8000/access-specification).

### Data Types

In this program, you will notice the usage of `void` and `String`. These are Java `data types`, and they tell Java what type of data a specific variable or value will be. In this case, stating `void` before a method tells Java not to expect a value to be returned from this method \(this is a _return type_\), and using `String[]` tells Java that the following variable will be an [array](http://localhost:8000/arrays) of Strings.

Learn more about data types in the [variables lesson](variables-and-primitive-types.md).

## Quiz

Which code segment is correct?

{% tabs %}
{% tab title="\#1" %}
```java
public class Hello {
    public void World()
        System.out.println("!");
}
```
{% endtab %}

{% tab title="\#2" %}
```java
public class Hello {
    public void World() {
        System.out.println("!");
    }
}
```
{% endtab %}

{% tab title="\#3" %}
```java
public class Hello {
    public World() {
        System.out.println("!");
    }
}
```
{% endtab %}

{% tab title="\#4" %}
```java
public class Hello {
    public void World() {
        System.out.println("!")
    }
}
```
{% endtab %}

{% tab title="Answer" %}
**2** is the correct response. Notice that each code block is wrapped in curly braces, the method `World` has a `void` return type, and that the code statement has a semicolon after it.
{% endtab %}
{% endtabs %}

