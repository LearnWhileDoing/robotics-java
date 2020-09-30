---
description: Reference library for the use of Color Sensors.
---

# Color Sensor Configuration

This document provides a reference library for the use of Color Sensors. To start off, be sure to get your program set up.
Check game manual part 1 for a list of game-legal sensors

First, be sure to get the necessary packages imported:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.ColorSensor;
```
Then, be sure to init the sensor:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class ColorSensorTest extends LinearOpMode {
    ColorSensor colorSensor;

    public void init() {
        colorSensor = hardwareMap.get(ColorSensor.class,"sensor");
    }
}
```
# Code Samples

### Get the values:
```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware;

@TeleOp
public class ColorSensorTest extends LinearOpMode {
    ColorSensor colorSensor;

    public void init() {
        colorSensor = hardwareMap.get(ColorSensor.class,"sensor");
    }

    public void loop() {
        telemetry.addData(colorSensor.argb())
    }
}
```
If you run this example, the sensor will print to the driver station screen the colors and alpha value it sees. You can also get the independant values with the `colorSensor.alpha()`, `colorSensor.red()`,`colorSensor.green()`, and `colorSensor.blue()` methods.

# Code Reference

|Method name|FTC Library Reference|Type|Parent|Description|Documentation|
|-|-|-|-|-|-|
|Alpha|`ColorSensor.alpha()`|`Method`|`ColorSensor`|Get the amount of light detected by the sensor as an int.|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#alpha--|
|Alpha, Red, Green, Blue|`ColorSensor.argb()`|`Method`|`ColorSensor`|Get the "hue" as an int|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#argb--|
|Blue|`ColorSensor.blue()`|`Method`|`ColorSensor`|Get the blue values detected by sensor as an int|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#blue--|
|Enable LED|`ColorSensor.enableLed(boolean)`|`Method`|`ColorSensor`|Enable the LED on the sensor. True to turn the light on, false to turn the light off. *Also check for a physical switch on the sensor|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#enableLed-boolean-|
|Get I2C Address|`ColorSensor.getI2cAddress()`|`Method`|`ColorSensor`|Get the I2C Address of the sensor|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#getI2cAddress--|
|Green|`ColorSensor.green()`|`Method`|`ColorSensor`|Get the green values detected by sensor as an int|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#green--|
|Red|`ColorSensor.red()`|`Method`|`ColorSensor`|Get the red values detected by sensor as an int|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#red--|
|Set I2C Address|`ColorSensor.setI2cAddress(I2cAddr)`|`Method`|`ColorSensor`|Set the I2C address to a value|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html#setI2cAddress-com.qualcomm.robotcore.hardware.I2cAddr-|

# Official Resources
[Official Docs](https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/ColorSensor.html)

# Unofficial Resources
[FTC Tricks](https://ftc-tricks.com/overview-color-sensor/)
