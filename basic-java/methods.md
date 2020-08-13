---
description: How we perform specific tasks
---

# Methods

A method is a set of commands that run when we _call_ it. Methods must be declared within a class, and are declared differently from a variable.

## Why methods?

Methods are run whenever they are called. That means that they can be called as many times as needed. Methods are used to be able to re-use code, and to separate your code into different sub-tasks to make it easier to read and understand. If you have your program divided up into methods that each perform a specific task, it will be more legible than a program that has all of its code under a single method.

## Method Declaration

Let's take a look at a method declaration.

```java
public void myMethod() {

}
```

### Header

The first line of that program is called the _method header_. The following are a few things it tells Java about the method.

#### Access Specifier

The first keyword, `public` is the access specifier. This tells Java where this method can be used. If the method is _public_, then it can be used anywhere the class is used. If it is _private_, then it can only be used **within** the class itself.

Why would we want to make a method private? Sometimes, we will use methods that should **only** be used by methods within the class. In order to signify this to Java \(and to ourselves\) we make the method private.

#### Return Type

Similar to data types for variables, return types are the type of data the method will _**return**_. The method above has the return type `void`. That means that this method will not return any value.

However, in the following example, the method `returns` a `String` value, so we must indicate that in the method header.

```java
public String greeting() {
    return "Hi!";
}
```

### Name

The first method has the name `main`. This means that we can call this method by writing `main()`.

### Parameters

Parameters allow us to pass values as _arguments_ to the method. These parameters are declared similarly to variables and are used similarly to variables as well. Here is an example of a method with parameters:

```java
public String copy(String str) {
    return str;
}
```

This method has a parameter `str` of data type `String`. Because it returns this variable, its return type must also be of type `String`.

## Method Body

Now that we understand what a method header shows and does, let's look into what we can make our method actually do.

Within a method, we can do all of our program logic!

* declare and assign variables
* execute commands and call methods
* perform conditional statements
* etc, etc.

## Calling methods

Depending on where a method is located, calling it is performed differently. Let's use an example class, `LightBulb`. We can either turn off or turn on a light bulb, and this is how we would do it.

```java
public class MyProgram {
    public void main() {
        LightBulb light = new LightBulb();
        light.turnOn();
        light.turnOff();
    }
}
```

First, we need to create an object of the class `LightBulb` that we will call light. Then, we call the method on it.

```java
LightBulb light = new LightBulb();
```

Notice that the _class_ we are in is `MyProgram`. We are a client of the class `LightBulb` and need to call our method accordingly. If we simply called the method `turnOn()`, our program would crash because the method does not belong to the class `MyProgram`.

We need to call the method on our `light` object like this:

```java
light.turnOn();
light.turnOff();
```

Say our class `MyProgram` now has a method, `turnLightOn()`. How would we implement this?

```java
public class MyProgram {
    public void main() {
        LightBulb light = new LightBulb();
    }
    public void turnLightOn(LightBulb light) {
        light.turnOn();
    }
}
```

Our method `turnLightOn()` has a parameter of type `LightBulb` and then turns that `light` on. Now, we can call that method from our class.

```java
public class MyProgram {
    public void main() {
        LightBulb light = new LightBulb();
        light.turnOff();
        turnLightOn(light);
    }
    public void turnLightOn(LightBulb light) {
        light.turnOn();
    }
}
```

As you can see, there are many ways to write and call methods.

{% hint style="info" %}
Remember that if a method belongs to a class we are a client of, you must call it on an object of that class.
{% endhint %}

### Returning a value

When a method _returns_ a value, it means that the method will give back a value to whatever called it.

```java
public void getGreeting() {
    String theGreeting = greeting();
}
```

In that example, the variable `theGreeting` is assigned to the value _returned_ by the `greeting()` method.

