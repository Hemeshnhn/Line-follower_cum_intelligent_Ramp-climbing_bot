# Autonomous Line Follower with Ramp Climbing

An autonomous differential-drive robot designed to follow black track lines and climb steep inclines. It uses an onboard IMU to measure pitch angle in real time, displays live telemetry on an OLED screen, and adjusts motor power to climb slopes over 12° without stalling.

---

## Features
- **Line Tracking:** IR sensors detect black lines on contrasting surfaces.
- **Incline Detection:** MPU6050 IMU calculates real-time pitch angle.
- **OLED Display:** Shows live tilt data (`Pitch deg`).
- **Ramp Climbing:** Dynamically increases motor torque for slopes up to and exceeding 12°.

---

## Hardware
- Arduino Uno / Nano
- MPU-6050 IMU Sensor
- IR Line Tracking Sensors
- L298N Motor Driver
- 2 × BO Geared DC Motors + Wheels
- 0.96" I2C OLED Display (SSD1306)
- Battery Pack & 2WD Chassis

---

## System Working & Methodology
- **Track Following:** The downward-facing IR sensor array continuously reads surface reflectivity to compute line position, steering the differential-drive wheels to stay centered.
- **Real-Time Pitch Estimation:** The onboard MPU-6050 calculates the instantaneous chassis tilt along the pitch axis and streams live angle values directly to the 0.96" OLED screen.
- **Flat Surface Navigation (< 10°):** Operates under standard PWM drive levels optimized for stable line alignment and low battery consumption.
- **Steep Incline Scaling (> 10°):** When the IMU detects a pitch angle entering steep territory (surpassing 10° up to 12°+), the controller increases drive torque to overcome gravitational resistance and wheel slippage, ensuring a smooth, uninterrupted ascent.

---

## Project Demo & Media
- [Watch Full Video Demonstration](https://drive.google.com/file/d/1KGQZSUcrgKG75Pnb6wlyFmzgy8sqIS9R/view?usp=drive_link)
