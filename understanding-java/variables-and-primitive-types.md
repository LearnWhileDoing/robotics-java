---
description: How we store and save data in Java
---

# Variables and Primitive Types

## What is a variable?

A _variable_ is a container that is used for storing values.

Consider this analogy: a variable is like a vocabulary notecard. One side of the notecard is used for the word, and the other side is used for definition of that word. Here is an example of that in practice. `int amount = 3;`

This line of code is called a _variable declaration_, and consists of a left and right-hand side.

* The left-hand side of a variable declaration has a data type \(`int`\) and a name \(`amount`\), in that order. This tells your computer that the variable `amount` has the data type `int`, which will never change.
* The right-hand side is the _value_ which the variable will store. In this case, the value will be 3.

> Values _can_ change, data types _cannot_.

## Data Types

In the above example, variable `amount` is the type `int`. What does that mean?

As the name suggests, different _data types_ specify what type of data can be assigned as the value to a variable. In Java, there are two kinds of data types: _primitive_ and _non-primitive_.

### Primitive Data Types

8 different primitive data types are available in Java. They consist of:

1. **boolean** - `true` or `false`
2. **int** - an integer value
3. **double** - a decimal value
4. **char** - a Unicode character
5. **long** - like `int` but used for longer numbers
6. **float** - like `double` with less precision
7. **byte** - like `int` but in the range of -127 to 128
8. **short** - like `byte` but with a range of -32,768 to 32,767

In most cases, only the first 4 of those types are used. The other 4 are mainly used when memory consumption on your computer is of utmost importance, which is not the objective of this course.

### Why is Java not purely OOP?

As explained, Java has 8 primitive data types, as does the C programming language. However, this breaks the first law of pure OOP languages:

> 1. Pre-defined types are objects

Those 8 primitive data types are _primitives_, meaning they are not _objects_. Furthermore, this means that you cannot directly call [methods](../basic-java/methods.md) on them, but must instead use helper classes instead.

## Quiz

{% tabs %}
{% tab title="Question" %}
How would you declare a variable `age`? _Hint: use the `int` data type_
{% endtab %}

{% tab title="Answer" %}
```java
int age = 15;
```
{% endtab %}
{% endtabs %}

\_\_

