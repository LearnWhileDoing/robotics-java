# More OpMode magic

## Controlling a Servo

### Limited Rotation Servo

A limited rotation servo can turn from 0 degrees to a certain amount of degrees. This range of rotation is represented by \[0, 1\], where 0 is 0 degrees and 1 is fully rotated.

To turn a servo, use the `setPosition()` method.

```java
Servo myServo = hardwareMap.get(Servo.class, "servo);
myServo.setPosition(0.5);
```

### Continuous Rotation Servo

Continuous rotation servos are like motors but they are servos. If you are using them for some reason, you must access then through the `hardwareMap` with the `CRServo` class.

```java
Servo crServo = hardwareMap.get(CRServo.class, "cr-servo");
```

Continuous rotation servos work like motors in the sense that they receive a power that makes them go fast, slow, or reverse. You use the `setPosition()` method to power a continuous rotation servo.

## Telemetry

Telemetry allows you to send and show data on the Driver Station app. This is typically used for debugging or troubleshooting. Telemetry is used through the `telemetry` variable available in the `OpMode` class and `LinearOpMode` class.

### `addLine`

To add a line of data to the telemetry log, use the `addLine` method.

```java
telemetry.addLine("Hello telemetry!");
```

### `addData`

The `addData` method works similarly to the `addLine` method. However, using the `addData` method formats the data like this: "CAPTION: VALUE".

```java
telemetry.addData("CAPTION", "VALUE");
```

### `update`

When the `update` method is called, the telemetry log data is cleared sent to the Driver Station app and appears on the screen. If you use the `update` method without adding more data to the telemetry log, then the telemetry on the Driver Station app will be empty.

```text
telemetry.update()
```

## Gamepad

The gamepad is available with the `gamepad1` and `gamepad2` variables in the `OpMode` and `LinearOpMode` classes. There are a lot of controls and buttons on a gamepad. For a full list, visit [https://ftctechnh.github.io/ftc\_app/doc/javadoc/com/qualcomm/robotcore/hardware/Gamepad.html](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Gamepad.html) and scroll down to "Field summary". That will provide you will all of the fields that represent controls on a gamepad and the variable type, with some extra utility fields.

