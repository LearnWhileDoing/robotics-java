---
description: Controlling motors with OnBot Java
---

# Moving your robot

In this lesson, you will learn how to control a motor. We won't be teaching you how to drive your robot, nor will this lesson teach you how to control your robot through the gamepad. However, it should give you a basic understanding of how motors are controlled with OnBot Java.

## Accessing a motor

To reference a motor in your code, you must use the `hardwareMap` and assign the motor to a variable.

```java
DcMotor myMotor = hardwareMap.get(DcMotor.class, "motor");
```

Now, the motor you assigned to the name "motor" in your hardware map configuration will be stored in the variable `myMotor`.

Remember to change "motor" to whatever name you assigned to your motor in your own configuration.

## Powering a motor

DC motors receive power to move. The more power it receives, the faster it will go. The range of power you can give to a `DcMotor` is \[-1, 1\] which is -1 to 1, inclusive.

To give power to a motor, we use the `setPower()` method.

```java
myMotor.setPower(0.5);
```

This will give the motor half power.

## OpMode with a motor

In Android Studio, go back to `MyFIRSTOpMode`. Your code should still look like this:

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;

@Autonomous
public class MyFIRSTJavaOpMode extends LinearOpMode {
    @Override
    public void runOpMode() throws InterruptedException {
    
    }
}
```

In the `runOpMode()` method, let's declare a `DcMotor myMotor` and assign it to a motor from the `hardwareMap`.

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;

@Autonomous
public class MyFIRSTJavaOpMode extends LinearOpMode {
    @Override
    public void runOpMode() throws InterruptedException {
        DcMotor myMotor = hardwareMap.get(DcMotor.class, "motor);
    }
}
```

Now, we `waitForStart()`.

```java
DcMotor myMotor = hardwareMap.get(DcMotor.class, "motor);

waitForStart();
```

After the START button is clicked, we will wait 1 second, or 1000 milliseconds, by using `Thread.sleep`.

```java
DcMotor myMotor = hardwareMap.get(DcMotor.class, "motor);

waitForStart();

Thread.sleep(1000);
```

{% hint style="danger" %}
It is highly advised that you never use `Thread.sleep` in TeleOp, but it is perfectly acceptable and often the best method to "wait" in Autonomous.
{% endhint %}

Now, we will set the power of `myMotor` to half speed. This happens \(theoretically\) instantaneously. Once the power is set, we will let it move at half speed for one second by using `Thread.sleep`.

```java
DcMotor myMotor = hardwareMap.get(DcMotor.class, "motor);

waitForStart();

Thread.sleep(1000);
myMotor.setPower(0.5);
Thread.sleep(1000);
```

{% hint style="info" %}
`Thread.sleep` does not pause the robot from moving. It pauses the OpMode code from running for the specified amount of time. It can be used when you know exactly how long an action must be performed by your robot.
{% endhint %}

Finally, we will set the power of `myMotor` to 0 to make it stop.

```java
DcMotor myMotor = hardwareMap.get(DcMotor.class, "motor);

waitForStart();

Thread.sleep(1000);
myMotor.setPower(0.5);
Thread.sleep(1000);
myMotor.setPower(0);
```

Go ahead and push this code to your Robot Controller phone. Try running it. Does the motor move for one second? If so, congratulations, you now know how to move a motor in OnBot Java!

## Challenge

You just learned how to run a single motor. Now, can you run two at the same time? Can you coordinate them? If you have a robot built, can you get it to turn?

Once you feel that you have mastered controlling motors, try to get your robot to move in a square. Then, get it to do the square in reverse. Can you do it using `for` or `while` loops?

