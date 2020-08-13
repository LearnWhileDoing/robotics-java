---
description: is-a vs. has-a
---

# Inheritance & Composition

In Java \(and most OOP languages\), there are two concepts relating to classes known as inheritance and composition. They help you to more efficiently plan out your code. Let's take a look at what inheritance and composition are.

## Inheritance

Suppose we have a class `Shape`. It has a name and a color.

```java
public class Shape {
    protected String name;
    protected String color;

    public Shape(String theName, String theColor) {
        name = theName;
        color = theColor;
    }
}
```

### `protected`

Earlier, we learned about access specification on methods and instance variables. However, we only discussed `private` and `public`. There is a third access specifier known as `protected`. A method or instance variable that is `protected` **can be accessed within the class but also by sub-classes**.

### Sub-classes

Later on, we discover a shape known as a `Rectangle`. Its name is "Rectangle", it has a color, but it also has a `width` and a `height`. A `Rectangle` _**is-a**_ `Shape`, so we will _inherit_ the `Shape` class.

We do this by using the keyword `extends`.

```java
public class Rectangle extends Shape {
    protected int width;
    protected int height;
    
    public Rectangle(int theWidth, int theHeight, String theColor) {
        super("rectangle", theColor);
        width = theWidth;
        height = theHeight;
    }
}
```

### `super`

When you inherit a class, you are _extending_ it. That's why we use the keyword `extends`. However, we mustn't forget that the class we are creating, called the sub-class, has a parent class, called the super-class. The super-class has a constructor that must be called within the constructor of the sub-class. To do so, we use the `super` method. This calls the constructor of the parent class with the provided parameters.

{% hint style="info" %}
A class can only have one parent class.
{% endhint %}

## Composition

We just learned that a sub-class can only inherit one class. However, think of a copier. It _is-a_ printer and scanner. But how can we represent this without extending two classes?

Composition is another pillar of OOP. Instead of thinking "a copier _is-a_ printer and a scanner", think "a copier _has-a_ printer and a scanner".

We can make a `Copier` class have two instance variables, one that _is-a_ `Printer` and one that _is-a_ `Scanner`.

```java
public class Copier {
    private Printer printer = new Printer();
    private Scanner scanner = new Scanner();
    
    public void print(Page page) {
        printer.print(page);
    }
        
    public Page scan() {
        return scanner.scan();
    }
    
    public void copy() {
        Page page = scan();
        this.print(page);
    }
}
```

Now, instead of having to inherit two classes which breaks the rules of OOP, we can use composition to have a class that uses the functionalities of both a `Printer` and a `Scanner`.

{% hint style="info" %}
Inheritance = _**is-a**_; Composition = _**has-a**_
{% endhint %}

