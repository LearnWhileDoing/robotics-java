---
description: Reference library for the use of Continuous Rotation Servos.
---

# Continuous Rotation Servo Configuration

This document provides a reference library for the use of Continuous Rotation Servos (henceforth refered to as *CRServos*). To start off, be sure to get your program set up.
Check game manual part 1 for a list of game-legal servos.

First, be sure to get the necessary packages imported:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware.CRServo;
```
Then, be sure to init the servo:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class CRServoTest extends LinearOpMode {
    CRServo armServo;

    public void init() {
        armServo = hardwareMap.get(crservo.class,"armServo");
    }
}
```
# Code Samples

### Spin at a set speed:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class CRServoTest extends LinearOpMode {
    CRServo armServo;

    public void init() {
        armServo = hardwareMap.get(crservo.class,"armServo");
    }

    public void loop() {
        armServo.setPower(0.65); // Look familiar from DcMotors? Good!
    }
}
```
If you run this example, the servo will turn at 65% speed.

But what if we want it to spin the other way? Again, there are 2 ways of doing this:

one:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class CRServoTest extends LinearOpMode {
    CRServo armServo;

    public void init() {
        armServo = hardwareMap.get(crservo.class,"armServo");
    }

    public void loop() {
        armServo.setPower(-0.65); // Look familiar from DcMotors? Good!
    }
}
```
Two:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class CRServoTest extends LinearOpMode {
    CRServo armServo;

    public void init() {
        armServo = hardwareMap.get(crservo.class,"armServo");
        armServo.setDirection(DcMotor.Direction.BACKWARD);
    }

    public void loop() {
        armServo.setPower(0.65); // Look familiar from DcMotors? Good!
    }
}
```
There are pros and cons to both. Number one is simple and easier to follow when debugging, but when not using concrete numbers (when using an input value, for example), it is better to use the first, so you don't need to change the sign of the variable.

# Code Reference
CRServos extend the DcMotorSimple interface. This means many of DcMotorSimple's methods work on CRServos.

|Method name|FTC Library Reference|Type|Parent|Description|Documentation|
|-|-|-|-|-|-|
|Servo Controller|`CRServo.getController()`|`Method`|`CRServo`|Returns the underlying servo controller on which this servo is situated.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/CRServo.html#getController--|
|Get Port Number|`CRServo.getPortNumber()`|`Method`|`CRServo`|Returns the port number on the underlying servo controller on which this servo is situated.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/CRServo.html#getPortNumber--|

Methods inherited from DcMotorSimple

|Method name|FTC Library Reference|Type|Parent|Description|Documentation|
|-|-|-|-|-|-|
|Set Direction|`CRServo.setDirection()`|`Method`|`DcMotorSimple`|Sets the logical direction in which this servo operates by default.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotorSimple.html#setDirection-com.qualcomm.robotcore.hardware.DcMotorSimple.Direction-|
|Get Direction|`CRServo.getDirection()`|`Method`|`DcMotorSimple`|Gets the logical direction in which this servo is operating|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotorSimple.html#getDirection--|
|Get Power|`CRServo.getPower()`|`Method`|`DcMotorSimple`|Gets the power setting the servo is currently running at.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotorSimple.html#getPower--|
|Set Power|`CRServo.setPower()`|`Method`|`DcMotorSimple`|Sets the power level of the servo, expressed as a fraction of the maximum possible power / speed supported according to the run mode in which the servo is operating. A setting of zero will make the brake.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/DcMotorSimple.html#setPower-double-|


# Official Resources
[Official Docs](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/CRServo.html)

# Unofficial Resources
[STEM Robotics](https://stemrobotics.cs.pdx.edu/node/4742) - Hard to use, but a really good code sample.
