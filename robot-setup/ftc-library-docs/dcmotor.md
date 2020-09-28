---
description: Reference library for the use of DC Motors
---

# DC Motor Configuration

This document provides a reference library for the use of DC Motors. To start off, be sure to get your program set up.
Check Game Manual part 1 for a list of game-legal motors

First, be sure to get the necessary packages imported:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware.DcMotor;

@TeleOp
public class Gamepads extends LinearOpMode {

    // Init our variables so they are in the necessary scope.
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake"); // Replace intake with whatever you called your motor in your robot configuration.
    }

    public void start() {
        // We don't have anything to put in here for now.
    }

    public void loop() {
        intakeMotor.setPower(0.65); // This is the most common and easiest way to set power to your motors.
    }

    public void stop() {
        // Again, nothing for this right now.
    }
}
```

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
|Set Zero Power Behavior|`DcMotor.setZeroPowerBehavior(DcMotor.ZeroPowerBehavior)`|`Method`|`DcMotor`|Sets the behavior of the motor when a power level of zero is applied.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotor.html#setZeroPowerBehavior-com.qualcomm.robotcore.hardware.DcMotor.ZeroPowerBehavior-


# Notes
The buttons, analog sticks, and triggers are represented a public member variables that can be read from or written to directly.

Analog sticks are represented as floats that range from -1.0 to +1.0. They will be 0.0 while at rest. The horizontal axis is labeled x, and the vertical axis is labeled y.

Triggers are represented as floats that range from 0.0 to 1.0. They will be at 0.0 while at rest.

Buttons are boolean values. They will be true if the button is pressed, otherwise they will be false.

The codes KEYCODE_BUTTON_SELECT and KEYCODE_BACK are both be handled as a "back" button event. Older Android devices (Kit Kat) map a Logitech F310 "back" button press to a KEYCODE_BUTTON_SELECT event. Newer Android devices (Marshmallow or greater) map this "back" button press to a KEYCODE_BACK event. Also, the REV Robotics Gamepad (REV-31-1159) has a "select" button instead of a "back" button on the gamepad.

The dpad is represented as 4 buttons, dpad_up, dpad_down, dpad_left, and dpad_right

Either one or two gamepads can be used. In each code sample, use `gamepad2` in the place of `gamepad1` when referencing the other gamepad. Drivers must initialize their gamepads by pressing either `start`+`a` for `gamepad1` or `start`+`b` for gamepad2 on their respective pads.

# Official Resources
[Official Docs](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Gamepad.html)
