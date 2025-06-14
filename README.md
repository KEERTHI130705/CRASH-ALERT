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
## 🔌 Hardware Connections

Here’s how all the components are connected to your Arduino Uno:

### 🛰 ADXL345 Accelerometer (via I2C)
| ADXL345 Pin | Arduino Uno Pin |
|-------------|------------------|
| VCC         | 3.3V             |
| GND         | GND              |
| SDA         | A4               |
| SCL         | A5               |

---

### 📡 SIM800L GSM Module (via SoftwareSerial)
| SIM800L Pin | Arduino Uno Pin | Notes                          |
|-------------|------------------|--------------------------------|
| VCC         | 5V (external)    | Use separate power supply      |
| GND         | GND              | Common ground with Arduino     |
| TXD         | D2 (rxPin)       | Use voltage divider (5V → 2.8V)|
| RXD         | D3 (txPin)       |                                |

---

### 📍 NEO-6M GPS Module (via AltSoftSerial)
| GPS Pin | Arduino Uno Pin | Description                     |
|---------|------------------|---------------------------------|
| VCC     | 5V               | Power supply                    |
| GND     | GND              | Common ground                   |
| TX      | D8 (RX)          | Arduino receives GPS data       |
| RX      | D9 (TX)          | Not used (AltSoftSerial TX)     |

---

### 🔔 Buzzer
| Buzzer Pin | Arduino Uno Pin |
|------------|------------------|
| +          | D5               |
| -          | GND              |

---

### 🔘 Push Button
| Button Pin | Arduino Uno Pin | Notes                         |
|------------|------------------|-------------------------------|
| One End    | D6               | Connected with INPUT_PULLUP   |
| Other End  | GND              |                               |

---

> ⚠ *Note:*  
> - SIM800L can be unstable with USB power — use a dedicated 5V 2A power source.
> - Add a voltage divider for Arduino TX → SIM800 RX to avoid damaging SIM800.

---

## 🌟 Future Enhancements

- Live GPS data tracking integration
- Android app interface
- Firebase cloud alert logging
- Accident severity classification using ML
