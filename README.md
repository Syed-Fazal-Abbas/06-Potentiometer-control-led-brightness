# Project 6: Potentiometer Controlled LED Brightness (PWM)

## Description
This is my sixth embedded systems project where I used a 
potentiometer to smoothly control the brightness of an LED — 
turning the potentiometer increases or decreases the LED's 
brightness.

## Hardware Used
- Board: Arduino Uno
- Potentiometer (10K)
- LED
- Resistor: 220 ohm
- Breadboard
- Jumper wires

## How It Works
The middle pin of the potentiometer is connected to Arduino's analog 
pin A0, which gives a value between 0-1023 depending on the 
potentiometer's position. This value is converted to the 0-255 PWM 
range using the map() function, then sent to the LED (pin 9) using 
analogWrite() — which smoothly changes the LED's brightness. The 
values are also printed on the Serial Monitor for testing.

## Code

​```cpp
int potPin = A0; // Potentiometer pin
int ledPin = 9;  // LED connected to PWM pin 9
int potValue = 0;
int brightness = 0;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  potValue = analogRead(potPin); // Read pot value (0-1023)
  brightness = map(potValue, 0, 1023, 0, 255); // Scale to PWM range
  analogWrite(ledPin, brightness); // Set LED brightness
  Serial.println(brightness);
  delay(10);
}
```

## Demo Video
[https://youtu.be/ix8-93fL72U?si=uep95bfFIuN8vleo]

## What I Learned
- How to use analogRead() to read a potentiometer's value
- Using the map() function to convert one range into another
- Controlling LED brightness with analogWrite() (PWM)
- Using the Serial Monitor for testing and debugging
