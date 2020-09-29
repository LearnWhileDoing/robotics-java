---
description: Reference library for the use of DC Motors
---

# DC Motor Configuration

This document provides a reference library for the use of DC Motors. To start off, be sure to get your program set up.
Check game manual part 1 for a list of game-legal motors

First, be sure to get the necessary packages imported:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware.DcMotor;
```
Then, be sure to init your motor:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class MotorTest extends LinearOpMode {
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake");
    }
}
```
# Code Samples

### Set power of a motor:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class MotorTest extends LinearOpMode {
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake");
    }

    public void loop() {
        intakeMotor.setPower(0.65);
    }
}
```
If you run this example, the motor will spin at 65% speed in the forward direction. But what if this is the wrong way? There are 2 ways to fix this:

One:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class MotorTest extends LinearOpMode {
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake");
    }

    public void loop() {
        intakeMotor.setPower(-0.65); // Adding a negative value will make the motor spin the other way.
    }
}
```
Two:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class MotorTest extends LinearOpMode {
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake");
        intakeMotor.setDirection(DcMotor.Direction.REVERSE);
    }

    public void loop() {
        intakeMotor.setPower(0.65);
    }
}
```
There are pros and cons to both. Number one is simple and easier to follow when debugging, but when not using concrete numbers (when using an input value, for example), it is better to use the first, so you don't need to change the sign of the variable. The second is also better when there are 2 motors facing opposite directions that you want to be assigned the same values.

Remember you can always reset the direction with
```java
intakeMotor.setDirection(DcMotor.Diretion.FORWARD);
```

### Run the motor with a gamepad joystick value:
This is the base to almost any TeleOp program. In fact, this code sample is taken from the TeleOp sample code in this course!

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.hardware.DcMotor;

@TeleOp
public class MyFirstTeleOp extends OpMode {
    DcMotor left;
    DcMotor right;

    public void init() {
        left = hardwareMap.get(DcMotor.class, "left");
        right = hardwareMap.get(DcMotor.class, "right");
    }

    public void loop() {
        left.setPower(gamepad1.left_stick_y); // Instead of a constant, we are using the variable returned from gamepad1.left_stick_y
        right.setPower(gamepad1.right_stick_y); // Instead of a constant, we are using the variable returned from gamepad1.right_stick_y
    }
}
```
If you want to learn more about this, go visit the TeleOp sample code. If your robot moves unexpectedly, you may need to change the directions of the motors, which you now know how to do!

### Run the motor with encoders:

Making a motor infinitely run at a set speed is all well and good, but what if you want the motor to go to a specific position?

First, let's learn how encoders work:
```java
public class MotorTest extends LinearOpMode {
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake");
        intakeMotor.setDirection(DcMotor.Direction.FORWARD); // Not necessary, but good practice to set the motor back to the correct direction.
    }

    public void loop() {
        intakeMotor.setPower(0.65);
        int position = intakeMotor.getCurrentPosition();
        telemetry.addData("Encoder position",position);
    }
}
```
You should see the position of the motor's encoder running up on your driver station phone.

In order to make the motor run to a specific position, we need to do three things: Tell the motor it's job is now to go to a position, tell the script how far to turn, and how fast to do so.

```java
public class MotorTest extends LinearOpMode {
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake");
        intakeMotor.setDirection(DcMotor.Direction.FORWARD); // Not necessary, but good practice to set the motor back to the correct direction.
        intakeMotor.setMode(DcMotor.RunMode.RUN_TO_POSITION);
    }

    public void loop() {
        intakeMotor.setTargetPosition(70); // You will need to determine this position
        intakeMotor.setPower(0.65); // You will also need to determine the speed, but don't go too fast: Speed = inaccuracy, which your motors will fight, causing possible stutters.

        int position = intakeMotor.getCurrentPosition();
        telemetry.addData("Encoder position",position);
    }
}
```
So there you have it! Be careful with any of these, and test whatever you create ad nauseam. Remember you will need an encoder plugged in for the encoder modes to work.
# Code Reference

The class DcMotor extends [DcMotorSimple](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotorSimple.html), which has some classes and methods of its own.

|Method name|FTC Library Reference|Type|Parent|Description|Documentation|
|-|-|-|-|-|-|
|Run Mode|`DcMotor.runMode`|`Static Class`|`DcMotor`|The run mode of a motor controls how the motor interprets the it's parameter settings passed through power- and encoder-related methods. Some of these modes internally use PID control to achieve their function, while others do not. Those that do are referred to as "PID modes".|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.RunMode.html|
|Zero Power Behavior|`DcMotor.ZeroPowerBehavior`|`Static Class`|`DcMotor`|ZeroPowerBehavior provides an indication as to a motor's behavior when a power level of zero is applied. (Basically coast or brake)|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.ZeroPowerBehavior.html|
|Direction|`DcMotor.setDirection()`|`Method`|`DcMotorSimple`|Direction allows you to change the default forward and backward rotation settings. Expects `DcMotor.Direction.REVERSE` or `DcMotor.Direction.FORWARD` as arguments.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotorSimple.Direction.html|
|Get Controller|`DcMotor.getController()`|`Method`|`DcMotor`|	getController() returns the underlying motor controller on which this motor is situated.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#getController--|
|Get Current Position|`DcMotor.getCurrentPosition()`|`int`|`DcMotor`|Returns the current reading of the encoder for this motor. Requires the motor mode to be Encoder-based.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#getCurrentPosition--
|Get Run Mode|`DcMotor.getMode()`|`Method`|`DcMotor`|Returns the current run mode for this motor|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#getMode--|
|Motor Configuration Type|`getMotorType()`|`Method`|`DcMotor`|Returns the assigned type for this motor.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#getMotorType--|
|Get Port Number|`DcMotor.getPortNumber()`|`Method`|`DcMotor`|Returns the port number on the underlying motor controller on which this motor is situated.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#getPortNumber--|
|Get Power Float|`DcMotor.getPowerFloat()`|`Method`|`DcMotor`|Returns whether the motor is currently in a float power level.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#getPowerFloat--|
|Get Target Position|`DcMotor.getTargetPosition()`|`Method`|`DcMotor`|Returns the current target encoder position for this motor.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#getTargetPosition--|
|Is Busy|`DcMotor.isBusy()`|`Method`|`DcMotor`|Returns true if the motor is currently advancing or retreating to a target position.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#isBusy--|
|Set Mode|`DcMotor.setMode(DcMotor.runMode)`|`Method`|`DcMotor`|Sets the current run mode for this motor|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#setMode-com.qualcomm.robotcore.hardware.DcMotor.RunMode-, https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.RunMode.html|
|Set Motor Type|`DcMotor.setMotorType()`|`Method`|`DcMotor`|Sets the assigned type of this motor.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#setMotorType-MotorConfigurationType-
|Set Target Position|`DcMotor.setTargetPosition`|`Method`|`DcMotor`|Sets the desired encoder target position to which the motor should advance or retreat and then actively hold thereat.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#setTargetPosition-int-|
|Set Zero Power Behavior|`DcMotor.setZeroPowerBehavior(DcMotor.ZeroPowerBehavior)`|`Method`|`DcMotor`|Sets the behavior of the motor when a power level of zero is applied.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#setZeroPowerBehavior-com.qualcomm.robotcore.hardware.DcMotor.ZeroPowerBehavior-|

# Official Resources
[Official Docs](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Gamepad.html)

# Unofficial Resources
[FTC Tricks](https://ftc-tricks.com/dc-motors/)
