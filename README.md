# Smart Automatic Street Light System using 8051

[cite_start]An embedded automation project designed to improve energy efficiency in public lighting infrastructure by utilizing sensor-based decision-making. [cite: 70]

## 📌 Overview
[cite_start]Traditional street lighting remains active throughout the night, leading to significant power wastage when no traffic is present. [cite: 74, 76] [cite_start]This project solves that problem by using an **AT89C51 microcontroller** to ensure lights only turn ON when it is dark **and** motion (vehicles or pedestrians) is detected. [cite: 77, 88]

## 🚀 Key Features
* [cite_start]**Dual-Condition Logic:** Lights activate only if the ambient light is low (Night) AND movement is sensed. [cite: 88, 94]
* [cite_start]**Ambient Light Detection:** Uses an LDR sensor to distinguish between day and night. [cite: 76, 80]
* [cite_start]**Traffic-Aware Sensing:** Integrated IR sensors monitor the presence of vehicles or pedestrians in real-time. [cite: 76, 82]
* [cite_start]**High-Power Switching:** Utilizes 5V relays driven by BC547 transistors to safely control high-brightness LEDs. [cite: 86, 103]

## 🛠️ Hardware Components
| Component | Quantity | Purpose |
| :--- | :--- | :--- |
| **AT89C51 Microcontroller** | 1 | [cite_start]Central logic processing unit. [cite: 99, 108] |
| **LDR (Light Dependent Resistor)** | 1 | [cite_start]Ambient light level sensing. [cite: 100, 108] |
| **IR Sensor Module** | 1+ | [cite_start]Motion/Traffic detection. [cite: 101, 108] |
| **5V Relay** | 5 | [cite_start]Electromagnetic switching for LEDs. [cite: 102, 108] |
| **BC547 Transistor** | 5 | [cite_start]Relay driver/switching. [cite: 103, 108] |
| **High-Brightness LEDs** | 6 | [cite_start]Represents the street light output. [cite: 104, 108] |

## 💻 Software Implementation
[cite_start]The system logic is written in **Embedded C** and follows a specific workflow: [cite: 90]
1. [cite_start]Read the analog/digital signal from the **LDR**. [cite: 91]
2. [cite_start]Read digital inputs from multiple **IR sensors**. [cite: 92]
3. Execute decision logic:
   ```c
   if (night && motion_detected) {
       turn_light_on(); // Trigger relay
   } else {
       turn_light_off();
   }
