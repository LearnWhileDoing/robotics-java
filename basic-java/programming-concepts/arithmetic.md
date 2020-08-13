---
description: Math is c00l
---

# Arithmetic

## Operators

Java uses a concept called _operators_ to perform _operations_ on values. There are different types of operators used for performing different operations, but in this lesson we will look at the 7 main arithmetic operators.

### Basic Arithmetic operators

```java
+     //addition
-     //subtraction
*     //multiplication
/     //division
%     //modulus (remainder)
```

## Using operators

Say we have a variable, `age`.

```java
int age = 10;
```

How would we add a year to this variable?

```java
age = age + 1;
```

In that code snippet, we reassign the variable `age` to the value of `age` plus one. That means that the new value of `age` will be **10 + 1 = 11**.

### Increment & decrement

There is, however, a more efficient way to do this operation.

```java
age++;
```

The **++ increment** operator adds one to whichever variable it is performed on. Similarly, the **-- decrement** operator subtracts one from whichever variable it is performed on.

You can also perform basic arithmetic with the following syntax:

```java
age += 5; // age = age + 5;
age -= 5; // age = age - 5;
age *= 5; // age = age * 5;
age /= 5; // age = age / 5;
age %= 5; // age = age % 5;
```

