# TeleOp

Now that you have learned how OpModes work, we can start to build our own unique, custom OpModes. We will now create a demo TeleOp, using ~~some~~ _a lot_ of boilerplate code that you will use in most \(if not all\) of your TeleOps.

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.hardware.DcMotor;

@TeleOp
public class MyFirstTeleOp extends OpMode {
    public void init() {
    }

    public void loop() {
    }
}
```

As you can see, we will be overriding the `init()` and the `loop()` methods. We are going to use the `init()` to access the `hardwareMap`. We will also be assigning a _direction_ to each motor. This is because the left motor will spin forwards on its axis while the right motor will spin backwards, assuming you are using a standard chassis.

```java
public class MyFirstTeleOp extends OpMode {
    DcMotor left;
    DcMotor right;
    
    public void init() {
        left = hardwareMap.get(DcMotor.class, "left");
        right = hardwareMap.get(DcMotor.class, "right");
        
        left.setDirection(DcMotor.Direction.FORWARD);
        right.setDirection(DcMotor.Direction.REVERSE);
    }

    public void loop() {
    }
}
```

{% hint style="info" %}
Although not required, it is good practice to use the hardware map in the `init()` method, before any other methods.
{% endhint %}

Now we have access to the left and right motors, but how do we interact with them? For this, we will need to use the gamepad.

```java
public void loop() {
    left.setPower(gamepad1.left_stick_y);
    right.setPower(gamepad1.right_stick_y);
}
```

How does this work? Each time the `loop()` method is called \(not instantaneously, typically a couple of milliseconds\), the values for `right_stick_y` and `left_stick_y` are updated. That means that the powers of the left and right motors will be updated accordingly as well. Let's put it all together.

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
        left.setPower(gamepad1.left_stick_y);
        right.setPower(gamepad1.right_stick_y);
    }
}
```

{% hint style="info" %}
If your robot moves unexpectedly, you can try switching the negatives on the powers.
{% endhint %}

Congrats, you have a working TeleOp! 🎉

