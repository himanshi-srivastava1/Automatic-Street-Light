# Smart Automatic Street Light System using 8051

An embedded automation project designed to improve energy efficiency in public lighting infrastructure by utilizing sensor-based decision-making.               

## 📌 Overview
Traditional street lighting remains active throughout the night, leading to significant power wastage when no traffic is present.                                  This project solves that problem by using an **AT89C51 microcontroller** to ensure lights only turn ON when it is dark **and** motion (vehicles or pedestrians) is detected..

## 🚀 Key Features
* **Dual-Condition Logic:** Lights activate only if the ambient light is low (Night) AND movement is sensed.                                    
* **Ambient Light Detection:** Uses an LDR sensor to distinguish between day and night.                                                         
* **Traffic-Aware Sensing:** Integrated IR sensors monitor the presence of vehicles or pedestrians in real-time.                              
* **High-Power Switching:** Utilizes 5V relays driven by BC547 transistors to safely control high-brightness LEDs.                                              

## 🛠️ Hardware Components
| Component | Quantity | Purpose |
| :--- | :--- | :--- |
| **AT89C51 Microcontroller** | 1 | Gentral logic processing unit.   |
| **LDR (Light Dependent Resistor)** | 1 | Ambient light level sensing. |                                                  
| **IR Sensor Module** | 1+ | Motion/Traffic detection.   |                                                  
| **5V Relay** | 5 | Electromagnetic switching for LEDs.   |                        
| **BC547 Transistor** | 5 | Relay driver/switching.  |                       
| **High-Brightness LEDs** | 6 | Represents the street light output. |                    

## 💻 Software Implementation
The system logic is written in **Embedded C** and follows a specific workflow:                        
1. Read the analog/digital signal from the **LDR**.                                
2. Read digital inputs from multiple **IR sensors**.                                     
3. Execute decision logic:
   ```c
   if (night && motion_detected) {
       turn_light_on(); // Trigger relay
   } else {
       turn_light_off();
   }
