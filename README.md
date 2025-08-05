# 📏  ultrasonic-distance-measurer-arduino

A simple distance measuring system using an **Ultrasonic Sensor (HC-SR04)** and **Thingzkit Mini** (Arduino-compatible). It calculates the distance to an object in front and prints it to the **Serial Monitor**.

---
# 🔧 Hardware Components

| Component           | Quantity |
|---------------------|----------|
| Thingzkit Mini      | 1        |
| HC-SR04 Sensor      | 1        |
| Jumper Wires        | As needed|
| USB Cable           | 1        |

---
## 🖥️ Software Requirements

- Arduino IDE
- No additional libraries required
- USB drivers for Thingzkit Mini

---
## 🧠 Setup Diagram

![WhatsApp Image 2025-07-24 at 20 59 19_a6d0c852](https://github.com/user-attachments/assets/53a09cce-657f-47a1-83e4-66bded1a974d)


- **VCC** → 5V  
- **GND** → GND  
- **TRIG** → Pin 27
- **ECHO** → Pin 15

---
## 📄 Source Code

```cpp

const int trigPin = 27;
const int echoPin = 15;

long duration;
int distance;

void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  // Send ultrasonic pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Measure duration and calculate distance
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.0343 / 2;

  // Output to serial monitor
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  delay(500); // Delay before next reading
}

````

---

## 🔎 Output Screenshot

- **Serail Monitor Output**

- Distance: 15.32 cm
- Distance: 16.04 cm
- Distance: 18.25 cm
- Distance: 14.91 cm

---

## 🚀 How to Run

- Connect HC-SR04 to Thingzkit Mini as per the diagram.
- Open Arduino IDE and paste the code above.
- Select the correct board and COM port.
- Upload the code
- Open Serial Monitor (Ctrl + Shift + M).
- Move your hand in front of the sensor and observe real-time distance in cm.

---

## 💡 Applications

- Smart parking systems
- Obstacle detection in robots
- Level measurement (water, grain)
- Security alert systems

----

## 📜 License
This project is licensed under the MIT License – see the ```LICENSE``` file for details.

---

## 👩‍💻 Author
Kaviya Murugan
🎓 ECE Engineering | 💡 Embedded & AI Enthusiast
🔗  [LinkedIn](https://linkedin.com/in/kaviyamurugan) | [GitHub](https://github.com/kaviya-3016)

---
