# Ultrasonic Sensor (HC-SR04)

## 1. Sensor Type
The Ultrasonic Sensor is a **Digital sensor**  
because it uses digital signals (HIGH / LOW) for triggering and receiving.

---

## 2. Working Principle & Calculation

The sensor works based on:
**Sound Wave Reflection (Echo)**

### How it works:
- The sensor sends ultrasonic waves
- The waves hit an object
- The waves reflect back to the sensor
- The sensor measures the time taken

### Formula:
Distance = (Speed × Time) / 2

In Arduino:
Distance = Time × 0.017

---

## 3. Datasheet & Voltage

- Operating Voltage: **5V**
- Measuring Range: **2 cm to 400 cm**

---

## 4. Pins & Connection

### Pins:
- VCC → Power
- GND → Ground
- TRIG → Trigger (Output)
- ECHO → Echo (Input)

### Arduino UNO Connection:
- VCC → 5V
- GND → GND
- TRIG → Digital Pin 4
- ECHO → Digital Pin 5

---

## 5. Circuit Implementation

- Connect the sensor to Arduino
- Check all connections carefully
- Run the simulation or real circuit

---

## 6. Arduino Code (Serial Monitor)

```cpp
int trigPin = 4;
int echoPin = 5;

long duration;
float distance;

void setup() {
  Serial.begin(9600);
  
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);

  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  delay(500);
}
  delay(500);
}
