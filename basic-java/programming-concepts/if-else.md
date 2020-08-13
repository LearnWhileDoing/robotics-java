---
description: if this then that
---

# Control Flow

Many times in your code you only want to perform specific actions under specific conditions. In these cases, you would want to use `if else` statements.

```java
boolean shouldMove = true;

if(shouldMove) {
    robot.move();
}
```

The above is an example of an `if` statement code block. It will only run if the given condition is met. In this case, if `shouldMove` is `true`, then we call `move()` on the robot object.

We can also execute code if the condition is _not_ met.

```java
boolean shouldMove = true;

if(shouldMove) {
    robot.move();
} else {
    robot.stop();
}
```

Now, if `shouldMove` is not `true` then the robot will `stop()`.

If your `if` statement only has one line of code, you don't have to use curly braces. It can look like this:

```java
if(shouldMove) robot.move();
// or
if(shouldMove)
    robot.move();
```

What if there are different conditions that we want to compare?

```java
boolean shouldGoForwards = true;
boolean shouldGoSideways = true;

if(shouldGoForwards) {
    robot.moveFowards();
} else if(shouldGoSideways) {
    robot.moveSideways();
} else {
    robot.stop();
}
```

If `shouldGoForwards` is true, then the robot will `moveForwards()`. Otherwise, if `shouldGoSideways` is true, then the robot will `moveSideways()`. If none of these conditions are met, then the robot will `stop()`.



