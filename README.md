# 🔧 6-Servo Motor Control Simulation using Tinkercad

In this project, I used Tinkercad to design a simple simulation circuit that controls 6 servo motors using Arduino.

## 🌀 How it works:

Each servo motor starts by rotating from 90° to 180°, then back to 0°, completing a 180° swap.

This movement happens smoothly over 2 seconds.

After that, all servos stop at 90° and stay in that position for the rest of the time.

## 📌 Tools & Components Used:

Arduino Uno (in Tinkercad)

6 Servo Motors

Basic code using the Servo library

## 🧠 What I learned:

How to control multiple servos at the same time.

How to use delays and angles to create smooth motion.

How to use Tinkercad to simulate circuits before building them in real life.

```cpp


#include <Servo.h>

int pos = 0;

Servo servo_9;
Servo servo_3;
Servo servo_5;
Servo servo_6;
Servo servo_10;
Servo servo_11;
Servo servo_12;

unsigned long startTime;

void setup()
{
  servo_9.attach(9, 500, 2500);
  servo_3.attach(3, 500, 2500);
  servo_5.attach(5, 500, 2500);
  servo_6.attach(6, 500, 2500);
  servo_10.attach(10, 500, 2500);
  servo_11.attach(11, 500, 2500);
  servo_12.attach(12, 500, 2500);
  startTime = millis();
}

void loop()
{
 
  if (millis() - startTime < 2000) { 
  // sweep the servo from 0 to 180 degrees in steps
  // of 1 degrees
  for (pos = 0; pos <= 180; pos += 1) {
    // tell servo to go to position in variable 'pos'
    servo_9.write(pos);
    servo_3.write(pos);
    servo_5.write(pos);
    servo_6.write(pos);
    servo_10.write(pos);
    servo_11.write(pos);
    servo_12.write(pos);
    // wait 5 ms for servo to reach the position
    delay(5); // Wait for 15 millisecond(s)
  }
  for (pos = 180; pos >= 0; pos -= 1) {
    // tell servo to go to position in variable 'pos'
    servo_9.write(pos);
    servo_3.write(pos);
    servo_5.write(pos);
    servo_6.write(pos);
    servo_10.write(pos);
    servo_11.write(pos);
    servo_12.write(pos);
    // wait 5 ms for servo to reach the position
    delay(5); // Wait for 15 millisecond(s) 
  }
  } else {
    
    for (pos = 180; pos >= 0; pos -= 1) {
    // tell servo to go to position in variable 'pos'
    servo_9.write(pos);
    servo_3.write(pos);
    servo_5.write(pos);
    servo_6.write(pos);
    servo_10.write(pos);
    servo_11.write(pos);
    servo_12.write(pos);
    while (true);
   
    }
  } 
}
```

<img width="1706" height="727" alt="Swanky Albar-Gogo" src="https://github.com/user-attachments/assets/9435c874-005b-4bf1-a82f-ccc2f6afe995" />


# 🦿 Humanoid Robot Walking Algorithm

This algorithm explains how the walking motion is achieved using servo motors (or actuators) in a bipedal humanoid robot.

## 🧠 Algorithm Steps:
1. Start in neutral standing position
2. Shift body weight to the **right leg** and make Right leg becomes the support leg.
3. Lift the **left leg** by rising it up.
4. Swing the **left leg forward** by extending the knee forward like taking a step.
5. Place the **left foot** on the ground.
6. Shift body weight to the **left leg**.
7. Lift and swing the **right leg** forward and repeat the process.
