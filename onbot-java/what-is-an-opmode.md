---
description: The code that tells your robot how it should behave.
---

# What is an OpMode?

An Operational Mode \(a.k.a. OpMode\) is a Java file that uses the FTC OnBot Java libraries. In an OpMode, you tell your robot what routines it should perform, and how it should act.

There are two kinds of OpModes, and both serve different purposes.

## TeleOp \(OpMode\)

TeleOp code is controlled by the driver of your robot through the game controller and the Driver Station phone.

A TeleOp program [extends the class](../advanced/java/inheritance-and-composition.md#inheritance) `OpMode`. The `OpMode` class provides us with 3 methods to **override**:

* `init()` - called when the INIT button is pressed on the Driver Station phone.
* `init_loop()` - called when the INIT button is pressed. Called repeatedly until the STOP button is pressed.
* `start()` - called when the START button is pressed.
* `loop()` - called when the START button is pressed. Called repeatedly until the STOP button is pressed.
* `stop()` - called when the STOP button is pressed.

In your OpMode program, you can add code for each of these methods. The code you add will control your robot.

{% hint style="info" %}
The term override refers to when the class you are extending already has a specific method that you want to re-implement in your new class.

For example, the `OpMode` class has a method `init()` by itself, but we need to _override_ it and use our own code.
{% endhint %}

## Autonomous \(LinearOpMode\)

Autonomous code is run completely through the robot. The human does not interact with the robot while using Autonomous code.

An Autonomous program [extends the class](../advanced/java/inheritance-and-composition.md#inheritance) `LinearOpMode`. The `LinearOpMode` class provides us with a single method to override:

* `runOpMode()` - runs once the INIT button is pressed.

The `LinearOpMode` class also gives us a couple of utility classes:

* `waitForStart()` - tells the robot to pause in your code until the START button is pressed
* `opModeIsActive()` - checks if the OpMode is still active. Returns `false` when the STOP button is clicked or the OpMode crashed, otherwise returns `true`. 

Unlike `OpMode` that runs the `loop()` function repeatedly, **`LinearOpMode` runs the `runOpMode()` method sequentially**, meaning that the code is run from top to bottom rather than until the STOP button is pressed.

