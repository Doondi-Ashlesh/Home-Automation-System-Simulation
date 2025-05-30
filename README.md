I# 🏠 IoT-Based Home Automation System (Proteus + Raspberry Pi Simulation)

---

## Description

This project simulates an **IoT-based Home Automation System** using **Proteus 8.9 Professional** and a **Raspberry Pi 4 Model B** as the core controller.

The motivation behind this project stems from the growing need to automate basic home functionalities such as lighting, ventilation, and gas leak detection. While automation is widespread in industrial settings, **affordable, flexible, and customizable solutions for homes are still underdeveloped**.

This system addresses that gap by demonstrating how:
- Motion detection,
- Light intensity,
- Temperature,
- and Gas levels

can all be monitored and acted upon intelligently — **making home environments smarter, safer, and more energy-efficient**.

The solution is also designed to be scalable, allowing integration of more sensors and IoT protocols in the future.

---

## Technologies & Integrations

### 🧠 Firmware & Controller
- **Raspberry Pi 4 Model B** – used as the main control unit in the simulation
- Simulated GPIO and SPI/UART logic for sensor integration

### ⚙️ Proteus Environment
- **Proteus 8.9 Professional**
  - Used for complete **circuit schematic design**, **component integration**, and **simulation testing**
  - Project file: `.pdsprj` (Proteus Design Suite Project)
 
# 🧰 Software Stack
- **Python 3**
- **Raspbian OS (on actual hardware)**

### 📦 Python Libraries

- `RPi.GPIO` – GPIO pin control  
- `spidev` – SPI communication with MCP3208  
- `serial` – UART communication with GSM  
- `time` – Delays and polling  


### 🧰 Hardware Components Simulated

| Component                  | Role                                                        |
|---------------------------|-------------------------------------------------------------|
| **MQ-2 Gas Sensor**       | Detects gas/smoke presence                                  |
| **PIR Motion Sensor**     | Detects human presence                                      |
| **LDR (with Resistor)**   | Measures room light intensity                               |
| **LM35 Temperature Sensor**| Measures room temperature                                   |
| **Relay Module (5V)**     | Switches DC motor (fan) on/off                              |
| **DC Motor (1000 RPM)**   | Acts as a fan                                               |
| **DC Buzzer (85 dB)**     | Triggers alarm on gas detection                             |
| **NPN Transistor**        | Used to switch buzzer                                        |
| **LED (Red)**             | Represents room light                                       |
| **MCP3208 ADC (12-bit)**  | Converts analog sensor outputs (LDR, LM35) to digital       |
| **L293D Motor Driver IC** | Controls DC motor safely via relay                          |
| **LM016L LCD (16x2)**     | Displays sensor data and system status                      |
| **GSM Module (UART)**     | Sends alert messages to a predefined host on gas detection  |

### Libraries Used in Proteus
- **Gas Sensor Library**
- **PIR Motion Sensor Library**

These libraries were required to simulate analog/digital behavior for respective sensors during the Proteus simulation.

---

## Execution in Proteus

### ⚙️ How to Run the Simulation

1. **Install Proteus 8.9 Professional** if not already installed.
2. Open the project:  
   `IOTMiniProject-HomeAutomation.pdsprj`
3. Press the **Run** button at the bottom left of the Proteus window.

### What to Test in Simulation

- Toggle logic states for **PIR**, **MQ-2**, **LDR**, and **LM35** using virtual inputs.
- Observe output behavior:
  - **Motion Detected** ➜ Activates temperature and light checks.
  - **Low Light** ➜ LED turns ON.
  - **High Temperature** ➜ Relay activates motor (fan).
  - **Gas Detected** ➜ Buzzer turns ON + Alert via GSM (on virtual terminal).
  - **All changes** are displayed on the **LCD screen** in real time.

###  Additional Notes

- All sensors are wired to the Raspberry Pi’s GPIO pins as per the logical mapping.
- Analog sensors (LM35, LDR) connect to **MCP3208** which communicates via SPI with the Pi.
- GSM module communicates over **UART**, and simulates sending alert SMS messages when dangerous gas is detected.

---

## Summary

This project showcases how an **affordable smart home automation system** can be prototyped and simulated using Proteus. It integrates environmental monitoring (light, heat, gas) and motion detection with real-world actions like switching fans/lights or alerting hosts in cases of hazards. With the potential to be expanded for real deployments using Python and actual Raspberry Pi GPIO, this project forms a strong foundation for future embedded or IoT-based automation work.

