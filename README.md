# iot

#include <Servo.h>

const int buttonPin = 2;  // The pin number for the push button
const int servoPin = 9;   // The pin number for the servo motor

Servo servo;
int angle = 0;
int prevButtonState = HIGH;
int buttonState;

void setup() {
  servo.attach(servoPin);
  pinMode(buttonPin, INPUT);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == LOW && prevButtonState == HIGH) {
    // Button pressed, change the servo position
    angle += 45;
    if (angle > 180) {
      angle = 0;
    }
    servo.write(angle);
    delay(100);
  }

  prevButtonState = buttonState;
}
[iottt.docx](https://github.com/saddamsssssssss/iot/files/12011429/iottt.docx)
