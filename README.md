# Smart Warm Air Regulator
Instrumentation Project 

An embedded control system designed to monitor ambient temperature and regulate warm airflow automatically using wireless communication and feedback logic.

---

## 📌 Project Overview

This project presents the design and implementation of a **smart home warm air regulation device** built around an ESP32 microcontroller.

The system measures environmental temperature, communicates wirelessly via Bluetooth, and controls airflow direction and heating state automatically according to a configurable setpoint.

The heating unit is simulated using LEDs, while airflow direction is managed through a motorized mechanism.

---

## 🎯 Objectives

The system is designed to:

- Monitor ambient temperature.
- Transmit sensor data wirelessly.
- Maintain temperature within a predefined deadband.
- Allow remote configuration of the temperature setpoint.
- Provide manual and automatic motor control.
- Ensure safe operation using hardware limit switches.

---

## ✨ Key Features

### 🌡 Wireless Temperature Monitoring
- Temperature acquisition using **LM35 / LM335** (analog) or **DHT11/DHT22** (digital).
- Real-time data transmission to smartphone or PC via Bluetooth.

### ♨️ Automatic Temperature Regulation
- Maintains temperature inside a **±5°C band** around the desired setpoint.
- Heating behavior is represented by LED indicators.

### 🔄 Adjustable Airflow Direction
- DC motor rotates the air outlet left or right.
- Direction is determined by control logic or remote commands.

### 🛑 Limit Switch Protection
- Switches at both ends of the motion range.
- Prevents mechanical overrun.
- Automatically reverses direction when activated.

### 📱 Wireless Control via Bluetooth
Users can remotely:
- Set the target temperature.
- Start or stop the motor.
- Request live temperature readings.

### 🧩 Expandable Design
The architecture allows adding:
- safety mechanisms  
- calibration routines  
- logging  
- advanced control algorithms  

---

## 🧠 Control Logic

The controller continuously performs the following steps:

1. Read ambient temperature.
2. Compare with the setpoint.
3. Apply deadband decision:

- If temperature < (setpoint − 5) → turn heater ON.
- If temperature > (setpoint + 5) → turn heater OFF.

4. Monitor limit switches to prevent over-travel.
5. Send updated information over Bluetooth.

---

## 🧱 System Architecture

| Component | Description |
|----------|------------|
| Controller | ESP32 |
| Temperature Sensor | LM35 / LM335 / DHT11 / DHT22 |
| Communication | Bluetooth Low Energy (BLE) |
| Motor Driver | Dual-channel relay module (optocoupled) |
| Limit Switches | Mechanical or capacitive |
| Output Indicators | LEDs for heater/fan status |

---

## 📡 Wireless Communication

Communication is established using **Bluetooth Low Energy (BLE)**.

Using a mobile application such as **Bluetooth Serial Terminal**, the user can:

- update temperature setpoint  
- manually control motor motion  
- read live telemetry  

---

## 🛠 Technologies Used

- ESP32  
- Arduino IDE  
- Embedded C / Arduino  
- Bluetooth BLE  
- Analog & digital temperature sensing  
- Relay-based motor control  

---

## 📂 Repository Structure (example)

