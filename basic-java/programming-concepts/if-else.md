---
description: if this then that
---

# Control Flow

## If/Else

Many times in your code you only want to perform specific actions under specific conditions. In these cases, you would want to use `if else` statements.

```java
boolean shouldTurnOn = true;

if (shouldTurnOn) {
    light.turnOn();
}
```

The above is an example of an `if` statement code block. It will only run if the given [condition](booleans.md#logical-expressions) is met. In this case, if `shouldMove` is `true`, then we call `move()` on the robot object.

We can also execute code if the condition is _not_ met.

```java
boolean shouldTurnOn = true;

if (shouldTurnOn) {
  light.turnOn();
}
else {
  light.turnOff();
}
```

Now, if `shouldTurnOn` is not `true` then the light will `turnOff()`.

Note that if your `if` statement only has one line of code, you don't have to use curly braces. It can look like this:

```java
if (shouldTurnOn) light.turnOn();
// or...
if (shouldTurnOn)
  light.turnOn();
```

Congratulations, you now know how to perform control flow within your programming!

## Multiple Branches

What if there are different conditions that we want to compare? When there are more than one outcome of a section of control flow in your code, it is considered to have _multiple branches_ because there are multiple ways the control flow could end \(kind of like a choose-your-own-adventure\). 

### If / Else-If / Else

One way of accomplishing this would be through the use of "else-if". It combines "else" with another "if" statement.

```java
int colorNum = 3;

if (colorNum == 3) {
  String color = "red";
  light.changeColor(color);
} else if (colorNum == 2) {
  String color = "green";
  light.changeColor(color);
} else if (colorNum == 1) {
  String color = "blue";
  light.changeColor(color);
} else if (colorNum == 0) {
  String color = "white";
  light.changeColor(color);
}
```

Depending on which number `colorNum` is set to, the light will be changed to that color.  The code above looks very confusing, however, and Java thankfully provides us with a much better way to do this.

### Switch Statement

In the above example, we have 4 "cases" of outcomes:

1. if `colorNum` is 3, the light should change to "red".
2. if `colorNum` is 2, the light should change to "green".
3. if `colorNum` is 1, the light should change to "blue".
4. if `colorNum` is 0, the light should change to "white".

Java provides us with the `switch` statement, which allows us to write out these cases in a way that makes much more sense.

```java
int colorNum = 3;

String color;
switch (colorNum) {
  case 3:
    color = "red";
    break;
  case 2:
    color = "green";
    break;
  case 1:
    color = "blue";
    break;
  case 0:
    color = "white";
    break;
}

light.changeColor(color);
```

First, we make a String variable `color`. This is the variable that we will use to change the color of the light following the `switch` statement. Inside the `switch` statement, there are 4 `cases`, each corresponding to a different branch. There is code inside of each "case", followed by the keyword `break`. This tells the `switch` statement that it is finished.

However, what if we wanted both `4` and `0` to change the light back to white? We can have multiple `cases` that perform the same code:

```dart
case 4:
case 0:
  color = "white";
  break;
```

Now we changed our minds, and we want all numbers except for 3, 2, and 1 to change the light to white. Using the `default` case within the switch statement will perform the code inside of this case if none of the other "cases" are met. The `default` case acts like an `else` statement with "if/else".

```dart
case 0:
default:
  color = "white";
  break;
```

## Inline decisions \(ternary\)

Sometimes, you may want to quickly assign a value to a variable depending on a certain condition. Consider the following example:

```java
int sidesAmount = 1; // amount of sides this shape has
String shapeType; // the type of shape
```

How can we quickly decide what type of shape this is, without using an if/else statement? Introducing the ternary expression. It uses the following syntax: `CONDITION? OUTCOME1 : OUTCOME2`. Here is an example of how you would use it with the given example:

```java
String shapeType = sidesAmount > 1? "Polygon" : "Circle";
```

As you can see, there are 3 parts to a ternary statement. The first part, the _condition_, accepts a boolean condition. If the boolean condition is `true`, the ternary expression will result with the first outcome. Otherwise, the ternary expression will result with the second outcome.

{% hint style="warning" %}
Note that you can only use one condition in a ternary expression. If you have multiple branches, you _can_ nest ternary expressions, but it is advised that you use if/else-if/else or switch statements instead.
{% endhint %}

## Challenge

{% tabs %}
{% tab title="Challenge" %}
Can you add more cases to the `switch` statement that make the light turn different colors?
{% endtab %}

{% tab title="Answer" %}
```java
// try adding your own colors!

switch (colorNum) {
  case 6:
    color = "yellow";
    break;
  case 5:
    color = "orange";
    break;
  case 4:
    color = "purple";
    break;
  case 3:
    color = "red";
    break;
  case 2:
    color = "green";
    break;
  case 1:
    color = "blue";
    break;
  case 0:
  default:
    color = "white";
    break;
}
```
{% endtab %}
{% endtabs %}

