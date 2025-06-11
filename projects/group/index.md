---
layout: default
title: Group Projects
description: Projects that highlight exceptional group work compared to other projects in this portfolio
---

# Portable Language Translator

**Team Members:** Cristian Palencia, [Include teammate names here if desired]  
**Date:** Spring 2025  
**Project Type:** Group Capstone Project

**Description:**  
The Portable Language Translator is a wearable system that facilitates real-time two-way communication between spoken languages (English, Spanish, Korean) and American Sign Language (ASL). Designed for portability and accessibility, the device integrates speech-to-speech translation and gesture recognition into a single unified interface using a Raspberry Pi 5, Google Cloud APIs, and machine learning models.

**Key Features:**
- Real-time **Speech-to-Speech Translation** (English, Spanish, Korean) using Google Cloud Speech, Translation, and Text-to-Speech APIs.
- **ASL Recognition** for five key gestures using a camera and LSTM-based gesture classification.
- **Touchscreen Interface** with volume control, language settings, and WiFi connectivity.
- Fully enclosed in a custom **3D-printed, battery-powered wearable** frame.

---

## System Architecture

**Hardware:**
- Raspberry Pi 5  
- USB Microphone, Camera, and Speaker  
- Touch Screen  
- 5000mAh Battery Pack  
- 3D-Printed Enclosure  

**Translation Pipeline:**
1. **Speech Input →** Microphone + WebRTC VAD  
2. **Speech-to-Text →** Google Cloud  
3. **Translation →** Google Cloud  
4. **Text-to-Speech →** Google Cloud  
5. **Output →** USB Speaker  

**ASL Gesture Pipeline:**
1. **Video Input →** USB Camera + OpenCV  
2. **Hand Landmark Detection →** MediaPipe  
3. **Gesture Recognition →** LSTM Model (TFLite)  
4. **Speech Output →** Synthesized audio  

**UI Built With:** PyQt5  
- Tabs: Translation | WiFi | Settings  
- Physical toggle button switches between ASL and Speech modes  

---

## Known Challenges & Technical Constraints

- **Internet Dependency:** Required for speech translation APIs  
- **Limited ASL Vocabulary:** Only 5 gestures recognized offline  
- **Battery Life:** ~3.1 hours on full charge  
- **Latency:** Speech (0.3–1.9s), ASL (~2.5s)  
- **Heat Buildup:** Raspberry Pi 5 heats up during extended use  
- **Audio/Video Limitations:** Background noise and poor lighting reduce accuracy  

---

### Future Work & Recommendations

- Expand ASL vocabulary to recognize more gestures  
- Integrate offline translation models for fully disconnected use  
- Improve camera calibration and lighting sensitivity  
- Enhance battery management and cooling strategies  

---

**GitHub:** [View Repository](https://github.com/cpalencica/PortableLanguageTranslator) 


