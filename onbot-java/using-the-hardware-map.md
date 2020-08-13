# Using the Hardware Map

In a previous lesson, you learned how to set up a hardware map configuration for your robot. Now, we will learn how to reference that hardware map in your code.

Before we get into accessing the hardware map, we must learn about how robot parts are represented in OnBot Java.

## Robot Parts in OnBot Java

For now, we will focus on the two most important components of a robot: motors and servos.

Most FTC Teams use DC Motors for their robots. In OnBot Java, DcMotors are [represented](../basic-java/classes.md#about-classes) as the class `DcMotor`. Servos are represented as the `Servo` class.

{% hint style="warning" %}
**Don't create a new instance of DcMotor or Servo in your code!** You must use the hardware map to reference your components.
{% endhint %}

## Accessing the Hardware Map

The hardware map is provided to us through the variable `hardwareMap`. This variable is available when you are using the `OpMode` or `LinearOpMode` classes.

How do you access a component with the hardware map? The `hardwareMap` provides us with a `get` method that lets us get the component in our code.

```java
DcMotor motor = hardwareMap.get(DcMotor.class, "motor");
```

As you can see, the `get` method accepts two parameters: the type of component and the name. When you are using a servo, the type of component is `Servo.class`; when you are using a DC Motor, the type of component is `DcMotor.class`. 

If you are using a different component, it is `COMPONENT.class` where COMPONENT is the class representation of the robot part.

