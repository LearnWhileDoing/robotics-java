---
description: We are clients to code that has already been written to us.
---

# Using Java Programs

## Non-primitive data types

One of the most basic code statements you can write in Java is as follows:

```java
int i = 0;
```

This declares the variable `i` with the data type `int` and a value of `0`. Integers are primitive data types, but what happens when we use non-primitive data types like `String`?

```java
String greeting = "hello";
```

Not much has changed, except we now use the `String` data type and pass a `String` as the value. Let's go further with this. Say we have an example class, `LightBulb`. How would we use `LightBulb` as a data type and pass it as a value?

```java
LightBulb light = new LightBulb();
```

You can see that we are essentially creating a "new" LightBulb to be stored by the variable `light`.

## Client of the class

By creating a "new" object, we are now a _client_ of a class. In the case of the `LightBulb` class, we are a "client" of the class LightBulb, and must use the methods accordingly.

In previous lessons, we have used the line `System.out.println()` to print to the console. In this case as well, we are "clients" to the `System.out` class.

Being a _client_ of a class or another program means that we are able to use parts of code without actually having to know how it works, as long as we know what it does. Take the `System.out.println()` method: we know that it prints to the console, but it doesn't matter exactly how it does it as long as it does it.

This works the same way for the `LightBulb` class. Say we can turn our `light` on and off with the methods `turnOn()` and `turnOff()`. We can call these methods like `light.turnOn()` and we know exactly what they will do, but we don't need to understand how they work in order to use them in our own code.

