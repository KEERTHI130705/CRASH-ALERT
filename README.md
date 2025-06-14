# 🚨 CrashAlert – Accident Detection & Emergency Alert System

*CrashAlert* is a smart safety system that detects accidents through an accelerometer and immediately sends emergency alerts via SMS and call using the SIM800 module. It’s built to reduce response times and save lives when every second counts.

---

## 💡 Project Overview

When a sudden impact is detected (based on acceleration magnitude), the system:
- Activates a buzzer to alert nearby people
- Sends an SMS to a predefined emergency contact
- Automatically makes a phone call
- Shares a Google Maps link with location (GPS module integration)

---

## 🛠 Tech & Components

- 🔌 *Arduino Uno*
- 📟 *SIM800L GSM Module*
- 📍 *NEO-6M GPS Module*
- 📈 *ADXL345 Accelerometer*
- 🔊 *Buzzer*
- 🛑 *Push Button*
- 📦 *Libraries Used:*
  - Wire.h
  - Adafruit_Sensor.h
  - Adafruit_ADXL345_U.h
  - TinyGPS++.h
  - AltSoftSerial.h
  - SoftwareSerial.h

---
---

## 🚀 How It Works

1. *Impact Detection*: Uses ADXL345 to calculate magnitude of acceleration.
2. *Trigger Alert*:
   - Turns on a buzzer.
   - Sends an SMS with location via SIM800.
   - Makes a call to the emergency contact.
3. *Manual Alert*: Button press also triggers alert manually.

---

## 🔧 Setup Instructions

1. *Connect hardware modules* to Arduino pins as defined in the sketch.
2. Upload crash_alert.ino to your Arduino using the Arduino IDE.
3. Make sure your SIM800 module has:
   - A working SIM with balance
   - Proper signal strength
4. Power it on and simulate a crash (shake it hard!) or press the button.

---


## 🌟 Future Enhancements

- Live GPS data tracking integration
- Android app interface
- Firebase cloud alert logging
- Accident severity classification using ML
