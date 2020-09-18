---
description: The most important parts of your Java program
---

# Classes

Java is an "object oriented program", which means that everything in Java is based around the concepts of _classes_ and _objects_. To further explain this, we are going to make our own Java program and create a class.

## Setting up Repl.it

[Open up repl.it](https://repl.it/languages/java10). Click the "Add File" button and name it `Car.java`. Now, enter the following code into the text editor.

```java
public class Car {

}
```

Go to the `Main.java` file, and replace the existing code with the following:

```java
public class Main {
  public static void main(String[] args) {
    Car myCar = new Car();
  }
}
```

## About Classes

Congrats! You just created an _instance_, or an _object_, of the Car class!

Let's look at the variable declaration. We can see that the variable `myCar` is declared with the data type `Car`. This tells Java that this variable will be an object of the class Car.

```java
Car myCar = new Car();
```

Here, we tell Java that the variable `myHouse` will be of the data type `House`. We haven't made the `House` class so this code won't work, but go ahead and try to make your own House class after this lesson!

```java
House myHouse = new House();
```

In the variables lesson, we learned about the 8 primitive data types in Java, and you will notice that neither `Car` nor `House` are any of those. That is because `Car` and `House` are classes, and are considered _non-primitive_. If you haven't noticed, type `String` is a class, and is therefore _non-primitive_ as well.

When we create an instance of a class, we tell Java to create a _new_ object. If we want a new car, we would write `new Car()`.

{% hint style="info" %}
Remember that **classes represent things or objects, as well as abstract things**. Things like motors, cars, clothing items, are things that can be represented as classes. Also, abstract things like errors, colors, or even Strings can be represented as classes.

In short, **classes should represent anything that there can theoretically be multiple "instances" of**.
{% endhint %}

## Creating the Car class

### Class Header

Whenever you create a new class, you will begin with the following line. Of course, you will change `MyClass` to whatever classname you need.

```java
public class MyClass {
```

This line is called the _class header_, and it is used to tell Java what your class is called, as well as which class you plan on [inheriting](../#whats-covered-in-this-course)[ and extending](../#whats-covered-in-this-course) and/or which interface you plan on [implementing](../advanced/coming-soon.md).

### Instance Variables

When we think about a car, what specific qualities belong to that car? Whatever makes a specific instance of a class unique is considered an _instance variable_, as it only belongs to one instance \(one object\) of the class.

In the case of a Car, what comes to mind is the _make_, _model_, _color_, and _year_ of the car. The make, model, and color of the car are all `String` values, while the year should be an integer.

Let's make these instance variables. This will be inside the Car class.

```java
public class Car {
  public String make;
  public String model;
  public String color;
  public int year;
}
```

{% hint style="info" %}
In the methods lesson, you learned about [access specification](methods.md#access-specifier) on methods. The same concept applies to instance variables.
{% endhint %}

### Constructor

Great, now our car has specific attributes that make it unique. However, there is no way to create an object with unique properties yet. As you can see, these instance variables don't have any values assigned to them.

To do this, we will write a class _constructor_. The constructor of a class is a special method \(with no return type\) called whenever a new instance of a class is created. Usually, we use constructors to assign values to our instance variables. This is what our constructor should look like inside the Car class.

```java
public class Car {
  public String make;
  public String model;
  public String color;
  public int year;

  public Car() {

  }
}
```

As we learned in the methods lesson, a method can take in different arguments and use them like variables in the method. We can do the same for constructors:

```java
public Car(String theMake, String theModel, String theColor, int theYear)
```

This is called a _parameterized constructor_ because it now has different _parameters_. We can use these parameters to assign values to the instance variables.

```java
public class Car {
  public String make;
  public String model;
  public String color;
  public int year;

  public Car(String theMake, String theModel, String theColor, int theYear) {
    make  = theMake;
    model = theModel;
    color = theColor;
    year  = theYear;
  }
}
```

Now we have a Car that has its own make, model, color, and year. We can now go back into the `Main.java` file and update the `myCar` variable declaration accordingly.

```java
public class Main {
  public static void main(String[] args) {
    Car myCar = new Car("Porsche", "Taycan", "blue", 2020);
  }
}
```

After adding the arguments to the variable declaration, we now have a blue 2020 Porsche Taycan stored as the variable `myCar`. Nice!

{% hint style="info" %}
Typically, classes are written in **PascalCase** as opposed to **lowercase**.
{% endhint %}

## Methods

Cars aren't considered very useful unless they can perform specific tasks. In Java, these tasks are written as methods. We will make the following methods for our Car class: _beep_ and _drive_.

Go back to our Car class, and write the following method:

```java
public void beep() {
  System.out.println("BEEP");
}
```

This can be written anywhere within the Car class, but methods are typically located underneath the constructor.

The `beep` method doesn't need to return anything back, so the `void` return type is used. Also, we want our Car to be able to be `beep`ed by the driver, so we must make it public to make it usable.

If we go back into our `Main.java` file, we can now call the beep method.

```java
myCar.beep();
```

In the console to the right, you should see **BEEP**. Your Car can now beep!

We can write the same method but with a different method name and a different `println` argument for the `drive` method like so:

```java
public void drive() {
  System.out.println("I am driving");
}
```

Now we can go back to the `Main.java` file and call the `drive` method as well.

```text
myCar.drive();
```

## Recap

We now have written a Car class that has instance variables for its specific qualities, and has methods that allow it to perform specific tasks. Nice work!

### Challenge

Can you write your own class, in a new file called `House.java`, that represents a House? Use instance variables like color, town, rooms, or any others that you can think of!

