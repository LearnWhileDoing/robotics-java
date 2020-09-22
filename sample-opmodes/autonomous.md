# Autonomous

In this sample, we will program our robot to move in a square. Like we did in the TeleOp example, we will start off with some boilerplate code.

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.hardware.DcMotor;

@Autonomous
public class MyFirstAuton extends LinearOpMode {
    public void runOpMode() {
    }
}
```

In this case, we will be overriding the `runOpMode()` method. Now we can declare our motors. We will also be assigning a _direction_ to each motor. This is because the left motor will spin forwards on its axis while the right motor will spin backwards, assuming you are using a standard chassis.

```java
public void runOpMode() {
    DcMotor left = hardwareMap.get(DcMotor.class, "left");
    DcMotor right = hardwareMap.get(DcMotor.class, "right");
    
    left.setDirection(DcMotor.Direction.FORWARD);
    right.setDirection(DcMotor.Direction.REVERSE);
}
```

We now need to wait for the player to click the PLAY button. To do that, we will use the `waitForStart()` method.

```java
public void runOpMode() {
    DcMotor left = hardwareMap.get(DcMotor.class, "left");
    DcMotor right = hardwareMap.get(DcMotor.class, "right");
    
    left.setDirection(DcMotor.Direction.FORWARD);
    right.setDirection(DcMotor.Direction.REVERSE);
    
    waitForStart();
}
```

A square has 4 sides. For this autonomous, we will use a for loop that runs 4 times.

```java
for (int i = 0; i < 4; i++) {
}
```

We will have the robot move forwards for one second, then turn. You will need to adjust the time that it takes for your robot to turn based on your own robot.

```java
for (int i = 0; i < 4; i++) {
    left.setPower(0.5);
    right.setPower(0.5);
    Thread.sleep(1000); // wait for 1000ms, or 1s
    
    /* brake */
    left.setPower(0);
    right.setPower(0);
    
    /* turn 90 degrees */
    left.setPower(0.5);
    right.setPower(0.5);
    Thread.sleep(500); // make sure to adjust this time!
}
```

Now, let's put it all together.

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.hardware.DcMotor;

@Autonomous
public class MyFirstAuton extends LinearOpMode {
    public void runOpMode() {
        DcMotor left = hardwareMap.get(DcMotor.class, "left");
        DcMotor right = hardwareMap.get(DcMotor.class, "right");
        
        left.setDirection(DcMotor.Direction.FORWARD);
        right.setDirection(DcMotor.Direction.REVERSE);
        
        waitForStart();
        
        for (int i = 0; i < 4; i++) {
            left.setPower(0.5);
            right.setPower(0.5);
            Thread.sleep(1000); // wait for 1000ms, or 1s
            
            /* brake */
            left.setPower(0);
            right.setPower(0);
            
            /* turn 90 degrees */
            left.setPower(0.5);
            right.setPower(0.5);
            Thread.sleep(500); // make sure to adjust this time!
        }
    }
}
```

Congrats, you have a working Auton program! 🎉

