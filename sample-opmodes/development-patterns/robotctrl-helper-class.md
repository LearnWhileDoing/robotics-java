# RobotCtrl Helper Class

## Objective

Your robot probably has some main central functionality. For starters, that most likely includes:

* Move vertically
* Move horizontally \(if using mecanum wheels\)
* Rotate

Wouldn't it be nice if, instead of calling specific methods on each wheel or each motor every time you wanted to move your robot, you could call a single method? Let's go over how to do that.

We will be creating a new class called `RobotCtrl`, pronounced robot control or robot controller. This class will have the following methods:

* `move(double speed)` - vertical movement
* `strafe(double speed)` - horizontal movement
* `rotate(double speed)` - rotation

```java
class RobotCtrl {
    public void move(double speed) {
    }
    
    public void strafe(double speed) {
    }
    
    public void rotate(double speed) {
    }
}
```

How will we implement this? First, the `RobotCtrl` object needs access to your wheels. We can do this by taking two `DcMotor`s as parameters in a parameterized constructor.

```java
class RobotCtrl {
    DcMotor leftWheel;
    DcMotor rightWheel;
    
    public RobotCtrl(DcMotor leftWheel, DcMotor rightWheel) {
        this.leftWheel = leftWheel; // assign parameter leftWheel to instance variable leftWheel
        this.rightWheel = rightWheel; // assign parameter lrightWheel to instance variable rightWheel
    }

    /* ... */
}
```

Now the `RobotCtrl` class can access the wheels obtained through the `hardwareMap`.

## Challenge

{% tabs %}
{% tab title="Task" %}
Can you implement these methods yourself, using the `setPower` method?
{% endtab %}

{% tab title="Solution" %}
```java
class RobotCtrl {
    DcMotor leftWheel;
    DcMotor rightWheel;
    
    public RobotCtrl(DcMotor leftWheel, DcMotor rightWheel) {
        this.leftWheel = leftWheel; // assign parameter leftWheel to instance variable leftWheel
        this.rightWheel = rightWheel; // assign parameter lrightWheel to instance variable rightWheel
    }

    public void move(double speed) {
        leftWheel.setPower(speed);
        rightWheel.setPower(speed);
    }
    
    public void strafe(double speed) {
        /* write this method based on how your chassis is configured */
    }
    
    public void rotate(double speed) {
        leftWheel.setPower(speed);
        rightWheel.setPower(-speed);
    }
}
```
{% endtab %}
{% endtabs %}

## In Use

Great, now you have a robot control helper class. You can use the class like so:

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.hardware.DcMotor;

@TeleOp
public class UsingRobotCtrlHelperClass extends OpMode {
    RobotCtrl robotCtrl;
    
    public void init() {
        DcMotor left = hardwareMap.get(DcMotor.class, "left");
        DcMotor right = hardwareMap.get(DcMotor.class, "right");
        
        right.setDirection(DcMotor.Direction.REVERSE);
        
        robotCtrl = new RobotCtrl(left, right);
    }

    public void loop() {
        robotCtrl.move(gamepad1.left_stick_y);
        robotCtrl.strafe(gamepad1.left_stick_x);
    }
}
```

With this TeleOp, you can `move` based on the y-axis of the left stick on your gamepad, and you can `strafe` based on the x-axis.

