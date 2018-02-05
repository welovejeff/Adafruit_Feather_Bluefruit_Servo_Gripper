# Adafruit Feather Bluefruit Servo Gripper
Created this because I needed a way to control a [Servo Gripper](https://www.sparkfun.com/products/13174) via my Bluefruit. Took me a little bit, but hopefully sharing this will save you time on your project.

## Set Up
First, goto [Adafruit's website](https://learn.adafruit.com/adafruit-feather-32u4-bluefruit-le/overview) and make sure that you've gone through the process of setting up your Arduino IDE.

### Hardware
I placed my gripper servo on A03, but feel free to change that in the code.
Line 110
```
myservo.attach(21); // Attaches Servo to A03 (pin 21)
```
Obviously place red power to pwr, and brown ground to grnd.

*Yes, I'm aware that the power is only 3.3v and the servo needs 5v, but it works well enough for my purposes*

### Software
Download or fork then download my folder from here and then run Adafruit_Feather_Bluefruit_Servo_Gripper.ino

That will open BluefruitConfig.h and packetParser.ccp along with it.

Upload to your Feather.

### Mobile
Download the Adafruit Bluefruit App for [iOS](https://itunes.apple.com/us/app/adafruit-bluefruit-le-connect/id830125974?mt=8) or [Android](https://play.google.com/store/apps/details?id=com.adafruit.bluefruit.le.connect&hl=en).

Connect to your Feather in the menu (make sure your BlueTooth is on, haha.)

Then goto controller, and hit one of the buttons! Pressing and holding a button will open the gripper, depress to close gripper.

Need it to stay open, just comment that out in line 199.
```
myservo.write(180); // BUTTON IS DEPRESSED, CLOSE GRIPPER
```

## Thanks
Many thanks to the [Arduino reference](https://www.arduino.cc/en/Reference/Servo) site that helped me understand the Servo commands.

And a huge shoutout to Adafruit for creating the command example in the Feather library for which this is code is mostly based on.
