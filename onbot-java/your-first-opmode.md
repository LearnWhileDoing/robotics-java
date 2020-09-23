---
description: The moment you've all been waiting for...
---

# Your FIRST OpMode!

Whew, that was a lot of learning. Congratulations on making it this far!

Hopefully it wasn't _too_ complicated and you understood what you have learned. If not, feel free to [reach out for help](../get-help-with-the-course.md).

Now we get to the fun part. You get to program your robot! We will be combining everything we have learned thus far and putting it to use. Are you up for the challenge?

{% hint style="info" %}
Psst! If you are looking for some sample OpModes, they are available in the project folder. In Android Studio, they are available under the "FtcRobotController" module in the package "org.firstinspires.ftc.robotcontroller.external.samples"
{% endhint %}

## Create your FIRST OpMode file

### Enable Auto Import

Android Studio has a handy feature called "Auto Import" that will automatically import classes from other packages into your code. To enable this feature:

1. Go to the Android Studio preferences/settings.
2. Select Editor → General → Auto Import
3. For "Insert imports on paste:", select "All".
4. For "Sow import popup for:", enable "classes" and "static methods and fields".
5. Enable "Add unambiguous imports on the fly".

### Create the OpMode class

1. Double-click on the "TeamCode" module. Double-click on the "java" folder.
2. Right-click on the "org.firstinspires.ftc.teamcode" package and go to New → Java Class.
3. Type in the name of your OpMode. Make sure "Class" is selected.
4. Hit enter.

You should now have a file with the following contents:

```java
package org.firstinspires.ftc.teamcode;

public class MyFIRSTJavaOpMode {
}
```

Now, you will need to extend the `LinearOpMode` class. Following `public class MyFIRSTJavaOpMode`, type `extends LinearOpMode`. When the import popup appears, choose the first option. Your file should look like this:

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;

public class MyFIRSTJavaOpMode extends LinearOpMode {
}
```

You should have a red line under the class header. Hover over the line and select "Implement members". Now, your code should look like the following:

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;

public class MyFIRSTJavaOpMode extends LinearOpMode {
    @Override
    public void runOpMode() throws InterruptedException {
    
    }
}
```

Lastly, we need to tell the Driver Station app that this is an Autonomous program. To do so, type `@Autonomous` above the class header. Your code should be like this:

```java
package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.Autonomous;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;

@Autonomous
public class MyFIRSTJavaOpMode extends LinearOpMode {
    @Override
    public void runOpMode() throws InterruptedException {
    
    }
}
```

You now have an OpMode! It doesn't do anything for now. However, let's push the code to our Robot Controller phone to make sure it works.

## Building and pushing

Make sure that the Robot Controller phone is connected to your laptop and that the laptop has USB debugging permission for the phone.

Towards the top of the Android Studio user interface, find green play button. This is called the "push" button; its purpose is to "push" the code onto the phone.

![](https://github.com/FIRST-Tech-Challenge/SkyStone/wiki/images/Creating-and-Running-an-Op-Mode-%28Android-Studio%29/RunTeamCode.jpg)

Android Studio will ask you to choose a target device to install the Robot Controller app with your OpModes. Make sure that you choose the correct target device. Click OK and Android Studio will build the APK file and install it on the Robot Controller app.

## Run your OpMode

Assuming you have successfully built and pushed the app to your phone, you can now run your OpMode.

Verify that your phones are still connected to each other. On the Driver Station phone, open the Autonomous dropdown list to see your OpModes. You should see `MyFIRSTOpMode`. Choose it as your OpMode.

When you are ready, tap the INIT button. \(If you have code in the `runOpMode()` method, the code before `waitForStart()` will execute.\) If you have code in the `runOpMode()` method after the `waitForStart()` method, click the start button. The OpMode should stop by itself.

If no errors occurred, then congratulations! You coded, built, pushed, and run your first OpMode! 👏

