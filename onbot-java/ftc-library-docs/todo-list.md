---
description: List of pages to be written.
---

# Todo List

This is a list of libraries that have not been converted to the learnwhiledoing/robotics-java style. If you are interested, willing, and capable of contributing, open a pull request on GitHub with your new file in the `robotics-java`/`onbot-java`/`ftc-library-docs` directory. Your file name should have no capital letters and spaces should be replaced by dashes.

List: (**Bold** are high priority, *italics* are low priority)
- [ ] Acceleration
- [ ] Analog Input
- [ ] Analog Output
- [ ] Android APIs (Accelerometer, gyro, orientation, soundpool, text-to-speech)
- [ ] Blinker / LED / Light
- [x] Color Sensor
- [x] CRServo
- [x] DcMotor
- [ ] **DcMotorEx** / **DcMotorControllerEx**
- [ ] Distance Sensor
- [ ] FTC Event Loop
- [ ] REV Hub Internal Sensors (IMU/gyro/orientation)
- [ ] Hardware Map
- [ ] *I2C Devices*
- [ ] Light Sensor
- [ ] Linear Op Mode
- [ ] OpMode
- [ ] ~PIDcoefficients~ (Deprecated)
- [ ] PIDFcoefficients
- [ ] PWM
- [x] Servo
- [ ] **Telemetry**
- [ ] Touch Sensor
- [ ] **Vuforia**
- [ ] **OpenCV**
- [ ] **Tensorflow/TFOD**
- [ ] Ultrasonic Sensor

### What makes a good contribution?
- Decent description of the library or piece of hardware
- Explain what packages and libraries need to be imported
- Give a code sample of how to init the device
- Provide at least one useful code sample, preferably a simple and complex one.
- Include a code reference table. This should include the Method name, the FTC Library Reference, the type, the parent package, the description, and the link to the official docs for that operator.
- At the bottom, include an official and unofficial resources section with at least one link. However, it is better to leave this blank than to provide a bad recource. Official recources should always include a link to FIRST's [javadoc pages](https://ftctechnh.github.io/ftc_app/doc/javadoc/).
- Write your page in decent markdown code, briefly explained on this page.

### Simple GitBook Markdown


For Headings:
```markdown
# Largest heading
## Medium heading
### Smallest heading
```
For *Italicized* text:
```markdown
*italicized text*
```
For **Bold** text:
```markdown
**bold text**
```
For ~strikethrough~ text:
```markdown
~strikethrough text~
```
For [link]() text: (Note: markdown also supports plain urls. If you place a url in the text, it will automatically make it a link. This only applies if you want to have text on your link)
```
[title](link)
```
For hints:
```
{% hint style="info" %}
Hello world
{% endhint %}

(also works for warning, danger, and success)
```
Code Blocks: Be sure to specify the language.
<pre><code>```java
// Your Java code in here.
```
</code></pre>

# Example Code Reference

|Method name|FTC Library Reference|Type|Parent|Description|Documentation|
|-|-|-|-|-|-|
|Max Position|`Servo.MAX_POSITION`|`Double`|`Servo`|The maximum allowable position to which a servo can be moved|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#MAX_POSITION|
|Min Position|`Servo.MIN_POSITION`|`Double`|`Servo`|The minimum allowable position to which a servo can be moved|https://ftctechnh.github.io/ftc_app/doc/javadoc/com/qualcomm/robotcore/hardware/Servo.html#MIN_POSITION|

# Official Resources
[Official GitBook Markdown Docs](https://docs.gitbook.com/editing-content/markdown)

# Unofficial Resources
[Markdown Guide](https://www.markdownguide.org/cheat-sheet/)
