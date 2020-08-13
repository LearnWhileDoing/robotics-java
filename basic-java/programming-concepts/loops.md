---
description: 'Do this, then do this, then do this, then do this...'
---

# Loops

Many times in your code you want to repeat a specific set of actions until something happens. In these cases, we use a concept called _looping_. There are many ways to write loops in Java.

## For Loops

For loops are used when you know how many times you want to perform this set of actions. An example would be that if you want your robot to move in the shape of a square, it would have to go forwards and turn 4 times. Using a for loop, we can perform the set of actions we want to repeat without having to type them over and over again.

This is how we would represent that without a for loop:

```java
robot.moveForwards();
robot.turn();
robot.moveForwards();
robot.turn();
robot.moveForwards();
robot.turn();
robot.moveForwards();
robot.turn();
```

And here is how we could write it using a for loop:

```java
for(int i = 0; i < 4; i++) {
    robot.moveForwards();
    robot.turn();
}
```

A for loop consists of 3 statements:

1. **Index Variable Initializer**: `int i = 0;` This is the variable that will be used to _index_ the for loop, or keep track of how many times it has run. In this example, we will start the index variable at 0, but it can be any number.
2. **Condition Statement**: `i < 4` This is a [logical expression](booleans.md#logical-expressions) that is checked _before_ each time the code inside the for loop is run. If the statement is true, then the for loop will run again. If the statement is false, then it will not run again.
3. **Index Augmenter**: `i++` This is what changes the index variable _after_ each time the code inside the for loop is run. It can increase or decrease the index variable by any amount.

## While Loops

When you do not know how many times you want your loop to run, you can use a while loop.

```java
boolean shouldMove = true;

while(shouldMove) {
    robot.move();
}
```

`while` statements are very similar to `if` statements in the sense that they run _if and only if_ the given condition is true. However, while loops run until the given condition is no longer true, or `false`.

In other words, while statements run _while_ the given condition is true.

## Do/While Loops

Sometimes, you know you want to run a set of actions _at least once_, but maybe not any more than once. In these cases you could choose to use a do/while loop.

Let's take an example scenario where you are coding a video game. You know the user wants to play at least once, but they may not choose to play again. How would we represent this in code?

```java
do {
    playGame();
} while(playAgain());
```

The code within the `do` block will always run at least once, and will run as long as the `while` condition is true.

## Break Statements

If you ever want to break out of a loop, you can tell the loop to `break`.

```java
int count = 0;

while(true) {
    if(count == 3) break;
    count++;
}
```

