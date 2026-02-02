# 🌍 Active Air Quality Monitoring Device  

A real-time **IoT-based air quality monitoring system** that measures key environmental parameters — **PM2.5**, **CO (Carbon Monoxide)**, **overall air quality**, **temperature**, and **humidity** — and displays them both on a **custom-built web dashboard** and a **0.96-inch OLED display** for local visualization.  

---

## 📦 Components Used  

| Component | Function | Description |
|------------|-----------|-------------|
| **ARDUINO UNO** | Main Controller | Handles sensor data acquisition.|
| **MQ-135 Sensor** | Air Quality (CO₂, NH₃, Benzene, Alcohol, etc.) | Detects general air pollutants and toxic gases, giving an approximate AQI value. |
| **MQ-7 Sensor** | Carbon Monoxide Sensor | Measures the concentration of CO gas in ppm. |
| **DHT22 Sensor** | Temperature & Humidity | Provides temperature (°C) and relative humidity (%) readings. |
| **GP2Y PM2.5 Sensor** | Dust Concentration Sensor | Measures particulate matter (PM2.5) levels in µg/m³. |
| **DS3231 RTC Module** | Real-Time Clock | Provides accurate timestamps for each sensor reading. |
| **0.96-inch OLED Display (I2C)** | Local Display | Displays live readings of AQI, PM2.5, CO, temperature, and humidity. |

---

## 🧠 Project Overview  

The **Active Air Quality Monitoring Device** continuously measures ambient environmental parameters and transmits them to a **web interface** hosted locally by the ESP8266.  
Data is also displayed simultaneously on a **0.96-inch monochrome OLED screen**, providing real-time physical feedback without requiring a browser connection.  

### Key Highlights:
- Real-time monitoring of **PM2.5, CO, AQI, Temperature, and Humidity**
- **OLED display** for instant local feedback
- **RTC integration** for accurate timestamping

---

## ⚙️ System Workflow  

1. **Sensor Data Acquisition**  
   - UNO reads data from:
     - MQ-135 → AQI (air quality)
     - MQ-7 → CO (ppm)
     - GP2Y → PM2.5 (µg/m³)
     - DHT22 → Temperature & Humidity  
   - DS3231 provides real-time clock data.

2. **Local Display (OLED)**  
   - The OLED shows key parameters like:
     ```
     AQI: 78
     CO: 1.9 ppm
     PM2.5: 45 µg/m³
     Temp: 27°C  Hum: 60%
     Time: 18:32:12
     ```

---

## 🧾 Data Representation  

| Parameter | Unit | Source | Range | Description |
|------------|------|---------|-------|-------------|
| PM2.5 | µg/m³ | GP2Y Sensor | 0–500 | Particulate matter concentration |
| CO | ppm | MQ-7 | 0–1000 | Carbon Monoxide level |
| AQI | Index | MQ-135 | 0–500 | Composite air quality index |
| Temperature | °C | DHT22 | -40–80 | Ambient temperature |
| Humidity | %RH | DHT22 | 0–100 | Relative humidity |
| Time | hh:mm:ss | DS3231 | Real time | Timestamp of readings |

---

## 🧰 Software & Libraries  

**Programming Environment:** Arduino IDE  
**Languages Used:** C/C++ (for firmware) & JavaScript (for web UI)  

### Required Libraries:
- `ESP8266WiFi.h` – Wi-Fi setup  
- `ESP8266WebServer.h` – Web server hosting  
- `DHT.h` – DHT22 temperature and humidity  
- `Wire.h` & `RTClib.h` – DS3231 RTC communication  
- `Adafruit_SSD1306.h` – OLED display driver  
- `Adafruit_GFX.h` – Graphics library for OLED text rendering  
- `ArduinoJson.h` – To send data to the web page in JSON format  

---

## 🖥️ Web Interface Files  

| File | Description |
|------|--------------|
| `index.html` | Main dashboard structure |
| `script.js` | Handles live data updates and graphs |
| `style.css` | Styling for web layout |
| `data.json` | Dynamic endpoint for live sensor readings |

---
