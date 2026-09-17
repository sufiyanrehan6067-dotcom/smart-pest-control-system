# Smart Pest Control & Humidity Monitoring System

**What it is:** An AI-assisted IoT system designed for a firm's agricultural land that continuously monitors field conditions and automatically responds to pest-risk conditions — reducing manual inspection and blanket pesticide spraying.

**What it does:** Simulates a 6-zone field network reading humidity, temperature, and soil moisture. A trained machine learning model scores live pest-risk probability per zone; once risk is sustained for several consecutive readings, the system automatically triggers a relay-controlled spray (or holds for manual operator approval), then tracks the zone's recovery back to normal. All activity is visible on a live monitoring dashboard.

**How it's built:**
- **Python** (NumPy/Pandas) for field simulation and the data pipeline
- **scikit-learn** — a trained Random Forest classifier for live pest-risk scoring, layered on top of validated threshold logic
- **MQTT-style messaging** — simulated publish/subscribe architecture (sensor → broker → dashboard), designed to map directly onto real ESP32 hardware
- **ipywidgets** — an interactive live dashboard (Google Colab) showing real-time per-zone status, risk scores, and alert/spray history

**Status:** Software fully built and validated (100% pest-risk detection, 0 false alarms, 99.9% model accuracy on simulated validation data). Hardware pilot planning in progress — two deployment options are being evaluated: a sensor-based node (ESP32 + environmental sensors) and a camera-based visual AI node (Raspberry Pi + camera module).
