# shs_research_proj
Smart Hydroponic Growth Detection System - Independent Research Project
This project automates plant monitoring and lighting control for a small-scale hydroponic system. Using a Raspberry Pi, camera module, and sensors, the system identifies the growth stage of basil plants and adjusts the environment accordingly.

---

## Project Objectives

- Automate the process of determining basil plant growth stages using computer vision.
- Adjust LED lighting based on plant growth phase (seedling, vegetative, flowering).
- Monitor and log temperature, humidity, and ambient light conditions.
- Store daily image and sensor logs for long-term tracking.

---

## Problem Description

Manually monitoring plant growth and adjusting environmental conditions in a hydroponic setup is inefficient. This project addresses the challenge of automating that process using Python.

---

## Related Work

Many indoor farming projects use timers or basic environmental sensors. This project draws inspiration from:
- [PlantCV](https://plantcv.danforthcenter.org/) for plant image analysis.
- DIY Arduino/Raspberry Pi grow box automations.
- Visual analytics dashboards that track environmental trends.

---

## Solution

This project combines multiple Python libraries and modules to control and monitor the hydroponic setup:

## Features:
- Daily photo taken using the Pi Camera with a white-light flash.
- Growth stage detection using OpenCV (green pixel ratio).
- Automatic adjustment of RGB LEDs based on growth stage.
- Temperature and humidity readings using DHT22.
- Ambient light readings using LTR-329 sensor.
- Daily logs saved for sensor data and plant analysis results.

## Methodology:
- **Color Distribution Analysis** – Detect green coverage to infer growth stage.
- **Time Series Logging** – Monitor and record sensor data over time.
- **Multivariate Decision Logic** – Combine sensor data and image analysis to decide LED profile.

---

## Technologies & Libraries

- Python 3.x
- OpenCV (`cv2`)
- `adafruit-circuitpython-dht`
- `adafruit-circuitpython-ltr329`
- Raspberry Pi GPIO (`board`, `digitalio`)
- datetime, os, time

---

## 📂 Project Structure
smart_hydro/
├── main.py                # Main script
├── hydro_utils.py         # Reusable sensor/camera/light functions
├── profiles.py            # Growth stage RGB lighting profiles
├── logs/
│   ├── images/            # Daily photos
│   └── sensor_log.csv     # Daily sensor data
└── README.md              # This file

---

## ▶️ How to Run

1. Connect your Raspberry Pi with:
   - Pi Camera Module
   - RGB LED lights (via MOSFETs or relay)
   - DHT22 sensor
   - LTR-329 ambient light sensor

2. Install required libraries (inside your virtual environment if using one):
   ```bash
   pip install opencv-python adafruit-circuitpython-dht adafruit-circuitpython-ltr329
