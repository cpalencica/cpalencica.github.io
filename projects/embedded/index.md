---
layout: default
title: Embedded Systems Projects
description: Projects focused on microcontrollers, IoT, real-time systems, and embedded hardware/software integration.
---

# Embedded Systems Projects

Explore my work with embedded platforms through academic, team-based, and personal projects involving real-time systems, IoT, and hardware-software co-design.

---

## Traffic Light – Kernel Module  
*A traffic control simulation using Linux kernel programming on the BeagleBone Black.*

**Technologies Used:** Linux Kernel Modules, GPIO, Interrupts, Character Device Interface, BeagleBone Black

**Description:**  
This project implements a Linux kernel module that simulates a traffic light system entirely in kernel space. LEDs (green, yellow, red) are controlled via GPIO pins, and physical button inputs trigger interrupt-based behavior to switch between traffic states and pedestrian crossing modes. The module includes a configurable character device interface to monitor or modify state behavior and LED cycle rates.

**Key Features:**
- LED control and button input directly from kernel space
- Multiple operating modes: standard traffic cycle, flashing red/yellow
- Pedestrian call button support with interrupt handling
- Adjustable timing for state transitions
- Character device `/dev/mytraffic` for configuration and monitoring

**Hardware Setup:**
- BeagleBone Black
- LEDs on GPIO pins: 44 (Green), 67 (Red), 68 (Yellow)
- Buttons on GPIO pins: 26 (Pedestrian), 46 (Mode Switch)

**GitHub:** [View Repository](https://github.com/yourusername/traffic-light-kernel-module)

<!-- ![Traffic Light](../assets/projects/traffic_light.jpg) -->


---

## Home Security System – Kernel Module  
*A motion-activated alarm system with buzzer and toggle switch, built on the BeagleBone Black.*

**Technologies Used:** Linux Kernel Modules, GPIO, Interrupts, Software PWM, Character Device, BeagleBone Black

**Description:**  
This project implements a home security system in kernel space using the BeagleBone Black. A motion sensor triggers a buzzer alarm via a software PWM signal when the system is "armed." The mode is toggled by a pushbutton, and the status is exposed via a character device interface. PWM is generated using a dedicated kernel thread.

**Key Features:**
- Kernel interrupt-based motion detection using a PIR sensor
- Pushbutton input to arm/disarm the system
- Software-generated PWM on a buzzer using `kthread`
- Character device for user-space status access

**Hardware Setup:**
- BeagleBone Black
- PIR Motion Sensor (HC-SR501)
- Pushbutton for arming/disarming
- Buzzer driven by software PWM

**GitHub:** [View Repository](https://github.com/cpalencica/SecuritySystem)  
**Demo:** [Watch Video](https://youtu.be/EEVpLaNmyOU)

<!-- ![Home Security System](../assets/projects/home_security.jpg) -->


---

## Ingestible "Smart Pill"  
*A FreeRTOS-based monitoring system for internal and external environmental conditions using an ESP32.*

**Technologies Used:** ESP32, FreeRTOS, UART, ADC, GPIO Interrupts, Thermistor, Photocell, Voltage Divider

**Description:**  
The Smart Pill is a compact embedded system designed to monitor temperature, light, battery voltage, and orientation as it passes through three distinct phases: before ingestion, inside the body, and after exit. LEDs visually indicate the current phase, and sensor data is transmitted over UART every 2 seconds. A button resets the system state and time.

**Key Features:**
- **Environmental Monitoring**: Thermistor for temperature, photocell for light levels, and voltage divider for battery status.
- **Orientation Detection**: Tilt behavior simulated with an interrupt-driven button.
- **State Management**: LED indicators represent pill states—ready (green), swallowed (blue), and exited (red).
- **UART Output**: Periodic data sent to host every 2 seconds using formatted strings.
- **FreeRTOS Design**: Task-based structure for modular sensing and data reporting.

**Hardware Setup:**
- ESP32 microcontroller
- Thermistor (temperature via ADC)
- Photocell (light via ADC)
- Voltage divider circuit for battery sensing
- Button to simulate tilt
- Button to reset system state
- Red, Green, Blue LEDs

**Software Overview:**
- Sensor tasks: read analog inputs and update global variables.
- LED task: updates pill status based on light thresholds and reset input.
- UART task: sends formatted sensor data to host console.
- ISRs: used for orientation and reset input handling.

**GitHub:** *[Coming Soon]*  
**Demo:** [Demo Video](https://drive.google.com/file/d/1Q0cmgKvMJzyynExxrp9cXvPJPhaWtwVe/view?usp=drive_link)  
**Presentation:** [Technical Presentation](https://drive.google.com/file/d/1WAg6dNmaZUGKDJ7yxstegLMrAWHKJhu-/view?usp=sharing)

<!-- ![Smart Pill System](../assets/projects/smart_pill.jpg) -->


---

## Smart Cat Collar  
*An IoT-enabled collar for pets that tracks activity levels and environmental metrics.*

**Technologies Used:** ESP32, BLE, IMU Sensor, I2C, OLED Display  
**GitHub:** [View Repository](https://github.com/yourusername/smart-cat-collar)  
<!-- ![Smart Cat Collar](../assets/projects/smart_cat_collar.jpg) -->

---

## FitCat – Activity Tracking for Cats  
*Wearable device and dashboard designed to monitor feline movement and encourage healthy activity.*

**Technologies Used:** Embedded C, Bluetooth, Step Counter Algorithms, Web Dashboard  
**GitHub:** [View Repository](https://github.com/yourusername/fitcat)  
<!-- ![FitCat](../assets/projects/fitcat.jpg) -->

---

## Secure E-Voting  
*A hardware-based electronic voting prototype prioritizing security, anonymity, and auditability.*

**Technologies Used:** Embedded C, Keypad Input, EEPROM Storage, Encryption Logic  
**GitHub:** [View Repository](https://github.com/yourusername/e-voting)  
<!-- ![E-Voting](../assets/projects/e_voting.jpg) -->

---

## Personal Assistive Robot  
*A personal robot with basic autonomous behavior and interaction capabilities for assistance tasks.*

**Technologies Used:** Embedded C/C++, Motor Control, Ultrasonic Sensing, Finite State Machine  
**GitHub:** [View Repository](https://github.com/yourusername/assistive-robot)  
<!-- ![Assistive Robot](../assets/projects/assistive_robot.jpg) -->

---
