This project implements an embedded fitness tracking system on the STM32L4 Discovery Kit. Using the LSM6DSL accelerometer, the system detects steps in real-time, computes distance traveled and calories burned, and displays results on a TFT LCD (SPI).

⚙️ Features

Step Detection Algorithm: Real-time signal processing of accelerometer data for accurate step count.

Metrics Calculation:

Distance = stride × steps (stride derived from user height).

Calories = distance × weight × MET (3.5 for walking).

Embedded Communication Protocols:

I²C for accelerometer data acquisition.

SPI for LCD output.

User Interface: Live updates on 1.8” TFT LCD, with UART output for logging/debugging.

Extensibility: Supports integration of GPS, BLE/WiFi, and additional biometric sensors for a full IoT fitness tracker.

🛠️ Tech Stack

Microcontroller: STM32L4S5VIT6 (ARM Cortex-M4)

Sensor: LSM6DSL MEMS Accelerometer & Gyroscope

Firmware: C (STM32CubeIDE), FreeRTOS task scheduling

Display: 1.8” TFT LCD (SPI interface)

Protocols: I²C, SPI, UART

📊 Results

Accurate step counting under walking and jogging scenarios.

Real-time performance with minimal latency.

Verified power-efficient operation suitable for wearable devices.
