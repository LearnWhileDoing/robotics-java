---
description: Reference library for the use of Telemetry.
---

# Telemetry

## Telemetry Configuration

This document provides a reference library for the use of Telemetry. To start off, be sure to get your program set up.

First, be sure to get the necessary packages imported:

```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode; // Yep! That's it!
```

There is no initializing that has to be done with Telemetry!

## Code Samples

### Hello World:

```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;

@TeleOp
public class TelemetryTest extends LinearOpMode {
    public void loop() {
        telemetry.addData("Message","Hello World!");
        telemetry.update();
    }
}
```

If you run this example, you should see `Message: Hello World!` on your driver station. Pretty easy right?

But what if you want it to do something useful? Lets make it read out the encoder values of a motor:

```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware;

public class TelemetryTest extends LinearOpMode {
    DcMotor intakeMotor;

    public void init() {
        intakeMotor = hardwareMap.get(DcMotor.class,"intake");
        intakeMotor.setDirection(DcMotor.Direction.FORWARD); // Not necessary, but good practice to set the motor back to the correct direction.
    }

    public void loop() {
        intakeMotor.setPower(0.65);
        int position = intakeMotor.getCurrentPosition();
        telemetry.addData("Encoder position",position);
        telemetry.update();
    }
}
```

## Code Reference

| Method name | FTC Library Reference | Type | Parent | Description | Documentation |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Add Action | `telemetry.addAction()` | `java.lang.Object` | `Telemetry` | In addition to items and lines, a telemetry may also contain a list of actions. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#addAction-java.lang.Runnable-](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#addAction-java.lang.Runnable-) |
| Add Data | `telemetry.addData()` | `Telemetry.Item` | `Telemetry` | Adds an item to the end of the telemetry being built for driver station display. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#addData-java.lang.String-org.firstinspires.ftc.robotcore.external.Func-](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#addData-java.lang.String-org.firstinspires.ftc.robotcore.external.Func-) |
| Add Line | `telemetry.addLine()` | `Telemetry.Line` | `Telemetry` | Creates and returns a new line in the receiver Telemetry. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#addLine--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#addLine--) |
| Clear | `telemetry.clear()` | `void` | `Telemetry` | Removes all items from the receiver whose value is not to be retained. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#clear--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#clear--) |
| Clear All | `telemetry.clearAll()` | `void` | `Telemetry` | Removes all items, lines, and actions from the receiver | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#clearAll--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#clearAll--) |
| Get Caption Value Separator | `telemetry.getCaptionValueSeparator()` | `java.lang.String` | `Telemetry` | Returns the string which is used to separate caption from value within a Telemetry Telemetry.Item. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#getCaptionValueSeparator--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#getCaptionValueSeparator--) |
| Get Item Value Separator | `telemetry.getItemSeparator()` | `java.lang.String` | `Telemetry` | Returns the string which is used to separate Telemetry.Items contained within a line. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#getItemSeparator--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#getItemSeparator--) |
| Get Transmission Interval | `telemetry.getMsTransmissionInterval()` | `int` | `Telemetry` | Returns the minimum interval between Telemetry transmissions from the robot controller to the driver station | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#getMsTransmissionInterval--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#getMsTransmissionInterval--) |
| Is Auto Clear | `telemetry.isAutoClear()` | `boolean` | `Telemetry` | Answers whether clear\(\) is automatically called after each call to update\(\). | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#isAutoClear--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#isAutoClear--) |
| Log | `telemetry.log()` | `Telemetry.Log` | `Telemetry` | Returns the log of this Telemetry to which log entries may be appended. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#log--](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#log--) |
| Remove Action | `telemetry.removeAction()` | `boolean` | `Telemetry` | Removes a previously added action from the receiver. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#removeAction-java.lang.Object-](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#removeAction-java.lang.Object-) |
| Remove Item | `telemetry.removeItem()` | `boolean` | `Telemetry` | Removes an item from the receiver telemetry, if present. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#removeItem-org.firstinspires.ftc.robotcore.external.Telemetry.Item-](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#removeItem-org.firstinspires.ftc.robotcore.external.Telemetry.Item-) |
| Remove Line | `telemetry.removeLine()` | `boolean` | `Telemetry` | Removes a line from the receiver telemetry, if present. | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#removeLine-org.firstinspires.ftc.robotcore.external.Telemetry.Line-](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#removeLine-org.firstinspires.ftc.robotcore.external.Telemetry.Line-) |
| Set Auto Clear | `telemetry.setAutoClear()` | `void` | `Telemetry` | Sets whether clear\(\) is automatically called after each call to update\(\). | [https://ftctechnh.github.io/ftc\_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html\#setAutoClear-boolean-](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html#setAutoClear-boolean-) |

## Official Resources

[Official Docs](https://ftctechnh.github.io/ftc_app/doc/javadoc/org/firstinspires/ftc/robotcore/external/Telemetry.html)

