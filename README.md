# Modular Smart Home Security System (IoT Project)

A modular, **IoT-based smart home security system** built with **CubeCell + LoRa**, custom **PCB design in OrCAD**, and sensors for motion, temperature, and gas detection.  
The project was developed as part of an Electrical & Computer Engineering program at **Technion – Israel Institute of Technology**.

---

## 🌍 Motivation
Traditional home security systems are often **closed, rigid, costly, and energy-hungry**.  
Our solution focuses on creating a **flexible, low-power, wireless, and scalable system** where users can easily add or remove modules based on their needs.

---

## 🎯 Goals
- Detect **motion, fire, and gas leaks** using independent sensor modules.  
- Enable **long-range wireless communication** with LoRa.  
- Run fully on **battery power** with efficient DC-DC converters.  
- Operate with **deep sleep mode**, waking only when events are detected.  
- Provide a **modular architecture** to easily expand with new sensors.  

---

## 📐 System Architecture
Each module includes:  
- **Battery + Charger (bq2403x)**  
- **DC-DC Converter (TPS63020)** – high-efficiency buck-boost regulator for stable 3.3V  
- **CubeCell AM02 MCU** – ARM Cortex M0+ with integrated LoRa radio  
- **LoRa Communication** – transmits alerts wirelessly to a central receiver  
- **Sensor** – PIR, LM35, or MQ-2 depending on module type  
- **Custom PCB** designed in OrCAD  

---

## 🔎 Sensors
- **PIR (AM312)** – Motion detection, 3–5 m range, ultra-low standby current (~15 µA).  
- **Temperature (LM35)** – Linear analog output (10 mV/°C), detects abnormal room temperature.  
- **Gas (MQ-2)** – Detects LPG, methane, propane, hydrogen, smoke (200–10,000 ppm).  

---

## 🧠 Algorithm
Each module is independent and event-driven.  

**State Machine:**  
1. **Sleep** – CubeCell remains in deep sleep to save energy.  
2. **Wake** – Sensor triggers interrupt when detecting motion, temperature spike, or gas.  
3. **Read** – CubeCell samples sensor data.  
4. **Transmit** – LoRa packet sent to central receiver.  
5. **Return to Sleep** – CubeCell goes back to low-power mode.  

FSM: **Sleep → Wake → Read → Transmit → Sleep**

---

## 🛠️ Tools & Technologies
- **Hardware Design:** OrCAD PCB Design  
- **Wireless Communication:** CubeCell AM02 + LoRa  
- **Power Management:** TPS63020 DC-DC converter, bq2403x charger IC  
- **Sensors:** PIR (AM312), LM35, MQ-2  
- **Programming:** Embedded C  
- **Debugging & Testing:** Oscilloscope, multimeter, LoRa serial monitoring  

---

