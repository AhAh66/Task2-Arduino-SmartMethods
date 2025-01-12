# Task 2: Design and Program a Digital Sensor Example

## Overview
This task demonstrates the design and programming of a digital sensor with an Arduino board. A push button is used as the digital sensor, which outputs either HIGH (1) or LOW (0) based on its state (pressed or not pressed). The Arduino reads the sensor state from a digital pin and controls an LED accordingly.

---

## Features
- Demonstrates the use of a digital sensor with Arduino.
- Implements a push button to detect ON/OFF states.
- Uses the button’s state to turn an LED ON when pressed and OFF when released.
- Highlights the simplicity and binary nature of digital sensors.

---

## Hardware Requirements
- Arduino board (e.g., Uno, Mega, Nano).
- Push button.
- 10kΩ pull-down resistor.
- LED.
- 220Ω resistor (for the LED).
- Breadboard.
- Connecting wires.

---

## Circuit Diagram
### Push Button Circuit:
1. Connect one leg of the push button to 5V.
2. Connect the other leg to:
   - Digital pin 2 on the Arduino.
   - A 10kΩ resistor leading to GND (as a pull-down resistor).

### LED Circuit:
1. Connect one leg of the LED to digital pin 8 on the Arduino.
2. Connect the other leg to GND through a 220Ω resistor.

---

## Code
```cpp
const int buttonPin = 2;   // Pin connected to the push button
const int ledPin = 8;      // Pin connected to the LED
int buttonState = 0;       // Variable to store button state

void setup() {
  pinMode(buttonPin, INPUT);  // Set the button pin as input
  pinMode(ledPin, OUTPUT);    // Set the LED pin as output

  Serial.begin(9600);         // Start serial communication
}

void loop() {
  buttonState = digitalRead(buttonPin);  // Read the state of the button
  Serial.println(buttonState);           // Output the state to Serial Monitor

  if (buttonState == HIGH) {             // If the button is pressed
    digitalWrite(ledPin, HIGH);          // Turn on the LED
  } else {                               // If the button is not pressed
    digitalWrite(ledPin, LOW);           // Turn off the LED
  }

  delay(100);  // Short delay for stability
}
```

---

## How It Works
### Push Button Operation:
1. When the button is pressed, it connects 5V to the input pin (2) on the Arduino, resulting in a HIGH state.
2. When the button is released, the pull-down resistor ensures the input pin is pulled to LOW (0V).

### Arduino Logic:
- The Arduino reads the state of the button (HIGH or LOW).
- If the state is HIGH, the LED connected to pin 8 turns ON.
- If the state is LOW, the LED turns OFF.

---

## Applications
- Controlling devices with buttons or switches.
- User input interfaces for Arduino projects.
- Event-based triggers in robotics and automation systems.

---

## How to Use
1. Assemble the circuit as described in the Circuit Diagram section.
2. Upload the provided code to your Arduino board using the Arduino IDE.
3. Open the Serial Monitor (9600 baud rate) to observe the button state (1 or 0).
4. Press the button to turn the LED ON; release it to turn the LED OFF.

---

## Circuit Simulation
You can view the circuit and its simulation on Tinkercad through this [link](https://www.tinkercad.com/things/example-simulation-link).

---

### Screenshots
<img src="https://github.com/user-attachments/assets/a3b919e3-38b5-4ad6-850f-222198140b96" alt="Push Button Circuit" width="300">
<img src="https://github.com/user-attachments/assets/1af47481-2ea1-4553-acbe-3537c52179be" alt="LED Circuit" width="300">
