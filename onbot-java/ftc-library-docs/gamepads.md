---
description: Reference library for the use of gamepads
---

# Gamepad Configuration

This document provides a reference library for the use of gamepads. To start off, be sure to get your program set up. Check Game Manual part 1 for legal gamepads.

```java
package org.firstinspires.ftc.teamcode;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.Gamepad;
```

# Code Reference

|Button name|FTC Library Reference|Datatype|Description|
|-----------|---------------------|--------|-----------|
|Left Stick Y|`gamepad1.left_stick_y`|`float`|This is the left stick on the gamepad's forward/back positions|
|Left Stick X|`gamepad1.left_stick_x`|`float`|This is the left stick on the gamepad's left/right positions|
|Right Stick Y|`gamepad1.right_stick_y`|`float`|This is the right stick on the gamepad's forward/back positions|
|Right Stick X|`gamepad1.right_stick_x`|`float`|This is the right stick on the gamepad's left/right positions|
|Joystick Deadzone|`gamepad1.joystickDeadzone`|`protected float`|If the motion value is less than this threshold, the controller will be considered at rest|
|Left Trigger|`gamepad1.left_trigger`|`float`|This is the left trigger on the gamepad (NOT the small top button)|
|Right Trigger|`gamepad1.right_trigger`|`float`|This is the right trigger on the gamepad (NOT the small top button)|
|Left Bumper|`gamepad1.left_bumper`|`boolean`|This is the left bumper (located over the trigger)|
|Right Bumper|`gamepad1.right_bumper`|`boolean`|This is the right bumper (located over the trigger)|
|DPAD Up|`gamepad1.dpad_up`|`boolean`\*|This is the DPAD up button|
|DPAD Down|`gamepad1.dpad_down`|`boolean`\*|This is the DPAD down button|
|DPAD Left|`gamepad1.dpad_left`|`boolean`\*|This is the DPAD left button|
|DPAD Right|`gamepad1.dpad_right`|`boolean`\*|This is the DPAD right button|
|DPAD Threshold|`gamepad1.dpadThreshold`|`protected float`|Although the DPAD buttons are technically floats, they are interpreted as booleans. DPAD Threshold determines the point at which the dpad is pressed|
|A button|`gamepad1.a`|`boolean`|This is the a button|
|B button|`gamepad1.b`|`boolean`|This is the b button|
|X button|`gamepad1.x`|`boolean`|This is the x button|
|Y button|`gamepad1.y`|`boolean`|This is the y button|
|Guide button (Large button in the middle of the gamepad)|`gamepad1.guide`|`boolean`|This is the start button. **Use with caution, on some Android configurations with some gamepads, pressing this button while the program is running will quit the driver station app.**|
|Left Stick Button|`gamepad1.left_stick_button`|`boolean`|This is when you press down on the left joystick. **Use with caution, it is hard to press this button without giving any x or y input**|
|Right Stick Button|`gamepad1.right_stick_button`|`boolean`|This is when you press down on the right joystick. **Use with caution, it is hard to press this button without giving any x or y input**|

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
