---
layout: default
title: Embedded Systems Projects
description: Projects focused on microcontrollers, IoT, real-time systems, and embedded hardware/software integration.
---

# Embedded Systems Projects

Explore my work with embedded platforms through academic, team-based, and personal projects involving real-time systems, IoT, and hardware-software co-design.

---

## Traffic Light – Kernel Module  

**Description:**  
This project implements a Linux kernel module that simulates a traffic light system entirely in kernel space. LEDs (green, yellow, red) are controlled via GPIO pins, and physical button inputs trigger interrupt-based behavior to switch between traffic states and pedestrian crossing modes. The module includes a configurable character device interface to monitor or modify state behavior and LED cycle rates.

**Technologies Used:** Linux Kernel Modules, GPIO, Interrupts, Character Device Interface, BeagleBone Black

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
**Demo:** [Watch Video](https://drive.google.com/file/d/1fBGXLANkpO7i2Bp05br930pbd9TTIFEB/view?usp=sharing)

<!-- ![Traffic Light](../assets/projects/traffic_light.jpg) -->


---

## Home Security System – Kernel Module  

**Description:**  
This project implements a home security system in kernel space using the BeagleBone Black. A motion sensor triggers a buzzer alarm via a software PWM signal when the system is "armed." The mode is toggled by a pushbutton, and the status is exposed via a character device interface. PWM is generated using a dedicated kernel thread.

**Technologies Used:** Linux Kernel Modules, GPIO, Interrupts, Software PWM, Character Device, BeagleBone Black

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

**Description:**  
The Smart Pill is an embedded system designed to monitor temperature, light, battery voltage, and orientation as it passes through three distinct phases: before ingestion, inside the body, and after exit. LEDs visually indicate the current phase, and sensor data is transmitted over UART every 2 seconds. A button resets the system state and time.

**Technologies Used:** ESP32, FreeRTOS, UART, ADC, GPIO Interrupts, Thermistor, Photocell, Voltage Divider

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

**Description:**   
A smart cat collar that records biometric data such as temperature and activity, displaying it in real time on a laptop chart and on an alphanumeric LED display.

**Technologies Used:** ESP32, I2C, Node.js, Socket.io, CanvasJS, C (embedded), Serial UART, GPIO interrupts, L293D motor driver

**Key Features:**
- Real-time biometric data collection (temperature, activity level)  
- Accelerometer-based activity detection with three states: Highly Active, Active, Not Active  
- Alphanumeric LED display shows cat’s name, activity status, and time spent in activity  
- Button-triggered display updates using GPIO interrupts  
- Thermistor for temperature measurement using voltage divider and ADC  
- Node.js server with Socket.io streams data to a web interface visualized with CanvasJS  
- Buzzer controlled via L293D H-bridge for alerts  

**Hardware Setup:** 
- ESP32 microcontroller with I2C-connected ADXL343 accelerometer and 14-segment alphanumeric display  
- Thermistor connected to ADC pin via voltage divider circuit  
- Push button connected to GPIO for display control  
- Buzzer connected through L293D motor driver controlled by ESP32 GPIOs  
- Laptop connects via serial UART to ESP32 for real-time data visualization  

**GitHub:** *[Coming Soon]*  
**Demo:** [Demo Video](https://drive.google.com/file/d/1fDqN_OaTaeUsbGNRtM6CE7A8nKshv5VA/view?usp=sharing)  
**Presentation:** [Technical Presentation](https://drive.google.com/file/d/1aFpp11RI6BVutXHhoSuAp_-T2tGB8Q2R/view?usp=drive_link)  

---

## FitCat - Activity Tracking for Cats

**Description:**   
A multi-cat activity tracking system using ESP32 collars that send activity data to a Raspberry Pi server, which provides real-time leaderboards and alerts via buzzers and displays.

**Technologies Used:** ESP32, Raspberry Pi, Node.js, UDP networking, Socket.io, CanvasJS, ESP-IDF, PiCam, WiFi, Tomato router with static IP and DDNS

**Key Features:**  
- Multiple ESP32 cat collars track activity and communicate via UDP over WiFi  
- Raspberry Pi server aggregates data, generates real-time leaderboards, and streams webcam video  
- Leader change alerts via buzzer and alphanumeric displays on collars  
- Web interface visualizes activity levels per cat with live bar graphs  
- Robust network setup with static IPs and DDNS for external access  
- PiCam integration for remote video monitoring  
- Dynamic buzzer activation only on leadership change events  

**Hardware Setup:**   
- ESP32-based Cat Trackers with accelerometers, 14-segment alphanumeric displays, and buzzers  
- Raspberry Pi running Node.js server and PiCam streaming video feed  
- Router configured with SSID "Group_5" and password "smartsys," with static IP assignments and DDNS  
- Laptop accesses the web dashboard and PiCam feed via network  

**GitHub:** *[Coming Soon]*  
**Demo:** [Demo Video](https://drive.google.com/file/d/1SprtTMUCdMtvfq51NJBhopZzlKO2zs8R/view)  
**Presentation:** [Technical Presentation](https://drive.google.com/file/d/1j2x-MTZJ48Ol8Pv8gB4jjld8CJDgwwId/view?usp=drive_link) 


---

## Secure E-Voting

**Description:**   
Implemented a network of ESP32 fobs that form a P2P UDP mesh and elect a leader using the Bully Algorithm. Votes are cast via IR communication from sender fobs to a receiver fob. The leader collects votes and forwards them to a Node.js server on a Raspberry Pi, which displays live vote counts on a web interface.

**Technologies Used:** ESP32, Raspberry Pi, Node.js, UDP networking, IR communication, Bully Algorithm, Socket.io, CanvasJS, TingoDB, WiFi

**Key Features:**  
- P2P UDP heartbeat communication among ESP32 fobs for leader election via Bully Algorithm  
- IR signal voting interface with visual vote options indicated by LEDs cycling every 4 seconds  
- Leader node aggregates votes and confirms vote reception to senders  
- Node.js server collects vote data and displays real-time results and logs in a browser  
- Hash table for IP to ESP32 ID mapping and active peer detection using UDP timeouts  
- Web interface uses Socket.io and CanvasJS for live vote visualization  
- Security considerations include device ID spoofing, IR eavesdropping, and Wi-Fi deauthentication mitigation

**Hardware Setup:**  
- ESP32 fobs with IR LED/receiver controlled by PWM via H-Bridge  
- Voting LEDs (red/green/blue) on sender fobs cycling through options  
- Leader indication LEDs (red/green)  
- Raspberry Pi running Node.js server connected via WiFi  

**GitHub:** *[Coming Soon]*  
**Demo:** [Demo Video](https://youtu.be/a0FYwbCRWlc)  
**Presentation:** [Technical Presentation](https://drive.google.com/file/d/11lCbSxFivGwoJSjbmf-UDrhI10iJ07x3/view?usp=drive_link)  



---

## Personal Assistive Robot

**Description:**   
Built a simple wheeled robot capable of navigating an indoor course defined by waypoints using Optitrack positioning and collision detection via a Sharp IR range sensor. The ESP32 controls motors through an H-bridge and implements PID control for waypoint following. A remote control mode using WASD keys is also supported.

**Technologies Used:** ESP32, Sharp IR Range Sensor, H-Bridge Motor Driver, Optitrack Motion Capture System, Node.js, UDP, PID Control

**Key Features:**   
- Real-time positioning via Optitrack system communicating coordinates over UDP  
- PID-based self-driving control to follow waypoints with heading correction  
- Collision detection using Sharp IR range sensor to stop robot if obstacle detected within 25 cm  
- Remote control mode toggled via button, enabling WASD keyboard control from a Node.js-hosted web app  
- Motor control implemented using PWM signals and GPIO pins on ESP32 through an H-bridge  
- Waypoint detection based on distance threshold (≤ 200 units) to advance navigation  

**Hardware Setup:**  
- ESP32 microcontroller as main processing and communication hub  
- Sharp IR Range Sensor for analog distance measurement and collision detection  
- Motors driven via H-bridge with PWM and GPIO control  
- Optitrack system for precise indoor position and orientation tracking  

**GitHub:** *[Coming Soon]*  
**Demo:** [Demo Video](https://drive.google.com/file/d/1pCS9vckuFYlIf6aCmPLMsRiZipL1e3xR/view?usp=drive_link) 


---
