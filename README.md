🌿 Automated Greenhouse System using ESP32 and Firebase
👨‍🔧 Developed by: Syed Khizar Zubair & Arqam Khan
📍 Department of Mechanical Engineering

📌 Project Overview
This project showcases a **fully autonomous greenhouse** system built using the **ESP32 microcontroller**. Designed with the vision of future smart agriculture, the system integrates **environmental sensors**, **automated actuators**, and **real-time cloud-based monitoring** using **Google Firebase**.

Our primary objective was to design an intelligent environment that autonomously manages itself—minimizing the need for human intervention in temperature, humidity, soil moisture, light, and irrigation control.

 🔧 Features
* 🌡️ Real-time temperature & humidity monitoring using **DHT11**
* 🌱 Soil moisture detection with analog sensor
* 💡 Light intensity monitoring using **LM393 Digital LDR**
* 🔊 Motion detection (optional: PIR or replaced with Ultrasonic)
* 🔄 Actuator control via relays:

  * Heating filament
  * LED Grow Light
  * Water Pump
  * Exhaust Fan (humidity-based)
  * Buzzer (alert)
    
* ☁️ **Firebase Integration**:
  * Live sensor data logging
  * Remote monitoring of all sensor inputs
  * Real-time actuator status tracking

🧰 Components Used

| Component              | Quantity | Purpose                        |
| ---------------------- | -------- | ------------------------------ |
| ESP32 Dev Board        | 1        | Main microcontroller           |
| DHT11 Sensor           | 1        | Temperature and humidity       |
| Soil Moisture Sensor   | 1        | Soil wetness sensing           |
| LM393 LDR Module       | 1        | Light level detection          |
| Ultrasonic Sensor      | 1        | (Optional) Replaces PIR motion |
| 4-Channel Relay Module | 1        | Controls actuators             |
| Fan                    | 1        | Activated by high humidity     |
| Buzzer                 | 1        | Alerts on motion               |
| Firebase (Cloud DB)    | -        | Real-time data sync            |

 🖥️ System Architecture

[ Sensors ] ---> [ ESP32 ] ---> [ Relays ] ---> [ Actuators ]
                     |
                 [ Firebase ]

📲 Firebase Features

Firebase Realtime Database stores:

  * Temperature
  * Humidity
  * Soil Moisture
  * Light Level
  * Ultrasonic/Motion status
  * Status of actuators
* View live updates remotely from any device

---

🧠 Smart Logic

| Condition                     | Action                   |
| ----------------------------- | ------------------------ |
| Temp < 20°C                   | Turn ON Heating Filament |
| Temp > 30°C or Humidity > 60% | Turn ON Exhaust Fan      |
| Light is Low                  | Turn ON Grow LED         |
| Soil Moisture < Threshold     | Turn ON Water Pump       |
| Motion/Obstacle Detected      | Activate Buzzer          |

---

🛠️ How to Run

1. Upload the `greenhouse_automation.ino` file to your ESP32 using Arduino IDE.
2. Install required libraries:

   DHT.h
   Firebase_ESP_Client.h
3. Connect to Wi-Fi and initialize Firebase credentials.
4. Monitor the serial console or Firebase dashboard for real-time data.



🔗 Libraries Required

cpp
#include <WiFi.h>
#include <DHT.h>
#include <Firebase_ESP_Client.h>

Install from Library Manager or manually add via ZIP.
💡 Future Improvements

* Add an OLED display or LCD for local status output
* Add mobile app interface via Blynk or MIT App Inventor
* Control through voice/AI assistant
* Implement AI-based irrigation logic (using predictive models)

