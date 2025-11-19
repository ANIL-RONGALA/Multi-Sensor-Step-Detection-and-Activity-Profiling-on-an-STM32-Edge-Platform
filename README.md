🚶 Step Counter & Pedometer on STM32 with FreeRTOS

An embedded systems project implementing real-time step detection, distance and calories measurement, and live telemetry using an STM32 microcontroller and FreeRTOS task scheduling.

📌 1. Overview

This repository provides a full implementation of a wearable-style step counter and pedometer using an STM32 microcontroller with FreeRTOS integration. The system supports:

Real-time accelerometer processing for step detection

Computation of distance traveled and calories burned

1.8″ TFT display for live metrics

UART output for logging / host communication

Modular firmware built in STM32CubeIDE / STM32 environment

FreeRTOS tasks for scheduler-based operation (allowing deterministic timing)

🛒 2. Hardware Components (BOM)
Component	Qty	Notes
STM32 microcontroller board (e.g., STM32L4 Discovery Kit)	1	MCU platform
MEMS Accelerometer + Gyroscope (LSM6DSL or similar)	1	Step sensor
1.8″ TFT LCD (SPI interface)	1	Display metrics
Supporting wiring, connectors, battery	—	Power and interface
(Optional) Bluetooth or USB interface	1	For logging/host comms
🖥️ 3. Software & Version Compatibility

Because FreeRTOS is free and open-source, it remains compatible across many STM32 toolchains. For best results:

STM32CubeIDE version 1.x – 2.x

STM32CubeMX integrated project configuration

FreeRTOS version latest stable (choose the one bundled or imported manually)

HAL / LL drivers suitable for the selected STM32 family

Note: FreeRTOS remains free; ensure the project uses the official FreeRTOS kernel (MIT licence) and that the toolchain supports it.

📥 4. Installation & Setup
Step 1 – Install STM32CubeIDE

Download and install from ST’s official site. Add support for your MCU/board.

Step 2 – Clone the Repository
git clone https://github.com/ANIL-RONGALA/Step-Counter-Pedometer-STM32-Embedded-System.git

Step 3 – Open the Project

In STM32CubeIDE: File → Import → STM32 Project → navigate to the cloned folder.

Step 4 – Build and Flash

Select the correct board/target, build the project, flash into the MCU, and monitor via UART or display.

Step 5 – Use the Device

Power the device, allow it to detect steps. The display will update live metrics; the UART/USB output will provide logs for step count, distance, calories.

📁 5. Repository Structure
Step-Counter-Pedometer-STM32-Embedded-System/
│
├── Core/                # source files (FreeRTOS tasks, drivers)
├── Drivers/             # HAL/LL drivers and BSP
├── 3rdParty/FreeRTOS/   # FreeRTOS kernel port
├── .project / .cproject # IDE project metadata
├── README.md            # (this file)

🎯 6. System Behavior & Features

Step Detection Algorithm: Uses accelerometer/gyro readings to detect human steps in real-time.

Distance Calculation: Estimates distance based on step count and user stride length (configurable).

Calories Estimation: Applies formula (distance × weight × MET) for calorie burn.

Display: Shows live step count, distance, calories on TFT LCD.

UART/USB Logging: Outputs metrics for host monitoring or data logging.

FreeRTOS Integration: Tasks configured for sensor sampling, display update, and logging — achieving real-time responsiveness and low latency.

🛠️ 7. Recreating the Project for Your Own Research

Fork/clone this repository.

Open in STM32CubeIDE and adjust board settings for your MCU.

Configure FreeRTOS task priorities and scheduling in FreeRTOSConfig.h.

Update hardware definitions (accelerometer interface, display pins) in driver files.

Build, flash, and test on your hardware.

Extend the project by adding new sensors (e.g., heart-rate monitor), BLE connectivity, or advanced analytics.

🚀 8. Future Scope & Research Extensions

Wearable Health Analytics: Integrate heart-rate, SpO₂, and movement intensity classification to create a full-suite fitness wearable.

Biomechanical Modeling: Use IMU data fusion and machine learning to classify gait patterns, detect anomalies or fall risk.

IoT & Cloud Integration: Add BLE/WiFi connectivity to upload metrics to cloud dashboards, enabling wellness tracking platforms.

Drone Motion Analytics: Adapt the architecture (step detection → motion detection) into a UAV context: accelerometer for vibration, IMU fusion for flight analytics, FreeRTOS tasks for flight control loops.

📘 9. Suggested GitHub Repository Name

STM32-StepCounter-FreeRTOS

Clear, descriptive, and suitable for academic portfolios.

📝 10. Acknowledgments

This project was developed using embedded systems best practices, combines sensor processing, real-time operating system architecture, and hardware-software co-design.

Note:
A portion of the documentation structure and wording was enhanced using AI tools for clarity.
All engineering design, algorithm implementation, and system architecture are original.
