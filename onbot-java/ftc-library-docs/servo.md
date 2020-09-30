---
description: Reference library for the use of Servos.
---

# Servo Configuration

This is for **Standard Servos**. If you need Continuous Rotation Servo details, visit the CRServo page.

This document provides a reference library for the use of Servos. To start off, be sure to get your program set up.
Check game manual part 1 for a list of game-legal servos.

First, be sure to get the necessary packages imported:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware.Servo;
```
Then, be sure to init the servo:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class ServoTest extends LinearOpMode {
    Servo armServo;

    public void init() {
        armServo = hardwareMap.get(servo.class,"armServo");
    }
}
```
# Code Samples

### Turn to a set position:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class ServoTest extends LinearOpMode {
    Servo armServo;

    public void init() {
        armServo = hardwareMap.get(servo.class,"armServo");
    }

    public void loop() {
        armServo.setPosition(0.65);
    }
}
```
If you run this example, the servo will turn to 65% of its max possible deflection. This can be changed using the REV Servo Programmer for REV Smart Robot Servos.

But what if you want it to turn based on your inputs? Lets use gamepad1's x and b buttons to make the servo spin in different directions.

```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class ServoTest extends LinearOpMode {
    Servo armServo;
    double servoPosition;
    double max_position;
    double min_position;

    public void init() {
        armServo = hardwareMap.get(servo.class,"armServo");
        max_position = 1; // Set this to the maximum desired (or possible) amount of turn. This will take trial and error.
        min_position = 0; // Set this to the maximum desired (or possible) amount of turn. This will take trial and error.
    }

    public void loop() {
        if(gamepad1.b && servoPosition < max_position) { // First, see if the button is being pressed. If it is, also make sure that our servo is within limits. If all that passes, increment the variable.
            servoPosition += 0.1 // Increment servo position by .1. If this is too slow, increase to .2, or use your own values
        } else if(gamepad1.x && servoPosition > min_position) { // First, see if the button is being pressed. If it is, also make sure that our servo is within limits. If all that passes, decrement the variable.
            servoPosition -= 0.1 // Decrement servo position by .1. If this is too slow, increase to .2, or use your own values
        }
        armServo.setPosition(servoPosition); // Set the servo to turn to the calculated position.
    }
}
```

{% hint style="danger" %}
Be careful with servos. Make sure you don't have them fighting themself or the robot. Depending on the brand you sprung for, your servo many end up destroying itself (stripping internal gears most likely) if not used carefully. Don't have your servo actively trying to do something that it is not capable of doing.
{% endhint %}

# Code Reference

|Method name|FTC Library Reference|Type|Parent|Description|Documentation|
|-|-|-|-|-|-|
|Max Position|`Servo.MAX_POSITION`|`Double`|`Servo`|The maximum allowable position to which a servo can be moved|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#MAX_POSITION|
|Min Position|`Servo.MIN_POSITION`|`Double`|`Servo`|The minimum allowable position to which a servo can be moved|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#MIN_POSITION|
|Get Controller|`Servo.getController()`|`Method`|`Servo`|Returns the underlying servo controller on which this servo is situated.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#getController--|
|Get Direction|`Servo.getDirection()`|`Method`|`Servo`|Returns the current logical direction in which this servo is set as operating.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#getDirection--|
|Get Port Number|`Servo.getPortNumber()`|`Method`|`Servo`|Returns the port number on the underlying servo controller on which this motor is situated.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#getPortNumber--|
|Get Position|`Servo.getPosition()`|`Method`|`Servo`|Returns the position to which the servo was last commanded to move.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#getPosition--|
|Scale Range|`Servo.scaleRange()`|`Method`|`Servo`|Scales the available movement range of the servo to be a subset of its maximum range.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#scaleRange-double-double-|
|Set Direction|`Servo.setDirection(Servo.Direction.DIRECTION)`|`Method`|`Servo`|Scales the available movement range of the servo to be a subset of its maximum range. Expects `Servo.Direction.FORWARD` or `Servo.Direction.BACKWARD` as arguments|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#setDirection-com.qualcomm.robotcore.hardware.Servo.Direction- SEE ALSO https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.Direction.html|
|Set Position|`Servo.setPosition()`|`Method`|`Servo`|Sets the current position of the servo, expressed as a fraction of its available range.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#setPosition-double-|


# Official Resources
[Official Docs](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html)

[FIRST Official Guide to Servos](https://github.com/ftctechnh/ftc_app/wiki/Controlling-a-Servo-(OnBot-Java) - Surprisingly not that great, but still works as a good source for syntax and general information.

# Unofficial Resources
[STEM Robotics](https://stemrobotics.cs.pdx.edu/node/4742) - Hard to use, but a really good code sample. They use some different syntax and practices then are taught in this course, but you can still take advantage of their use of certain methods and comments.
