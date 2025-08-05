---
layout: default
title: Internship Projects
description: Projects developed during industry internships, focused on applied R&D, embedded systems, UX design, and component benchmarking.
---

Explore selected technical work completed during my internships. These projects span biomedical sensing, user interface engineering, and component-level evaluation across multidisciplinary teams.

---

**Jump to Project:**  
[Hematocrit Detection](#hematocrit-detection)  
[System UI](#system-ui)  
[Component Evaluation](#component-evaluation)

---

## Hematocrit Detection

**Description:**  
Developed a system to detect the hematocrit boundary in a centrifuged blood sample using infrared laser refraction and spectral analysis. The system applies **Snell’s Law** to identify changes in refractive index between red blood cells and plasma, allowing for non-contact hematocrit detection via laser path deviation and spectrometer measurements.

**Technologies Used:** Raspberry Pi, Python, Spectrometer (Ocean Optics), Stepper Motor, I2C DAC, Tkinter, Matplotlib, Gaussian Curve Fitting, 8020 Aluminum Frame Construction

**Key Features:**
- **Snell’s Law–based Detection**: Laser refraction through the blood sample changes as it passes through different regions; refraction data reveals hematocrit location.
- **Spectral Analysis**: Real-time spectrum capture with peak detection using Gaussian fitting to identify laser deviation.
- **Motorized Scanning**: Stepper motor advances the laser along the vial for vertical scanning.
- **Dynamic Laser Control**: Laser intensity is auto-adjusted using a DAC to maintain optimal signal strength based on prior spectral data.
- **Graphical User Interface**: Tkinter-based GUI allows real-time plot viewing, intensity control, and parameter tuning.
- **Data Logging**: CSV logs of Gaussian peak centers and full spectral data for offline analysis.

**Hardware Setup:**  
- **Raspberry Pi** as central controller  
- **5V Laser** directed through a centrifuged vial  
- **Stepper Motor** for vertical laser scanning  
- **Spectrometer** to capture refracted beam spectra  
- **DAC (via I2C)** for adjusting laser power  
- **Physical housing** built using 80/20 aluminum extrusion frame to align all components

**Software Flow:**
1. **Initialization**: Configure spectrometer, motor, and DAC; create GUI plotting window  
2. **Spectral Capture**: Record intensity at each scan point  
3. **Laser Adjustment**: Tune laser power based on peak strength  
4. **Scanning**: Move laser vertically to scan blood sample  
5. **Signal Processing**: Smooth spectrum, fit Gaussian, extract peak wavelength
6. **Data Collection**: Save all positions, peak wavelengths, and spectra to timestamped directory

**GitHub:** [View Repository](https://github.com/cpalencica/HCT)

---

## System UI

**Description:**  
Created a Python GUI application for the P1A system that enables users—especially those less familiar with coding—to run specific commands and build command sequences through an intuitive interface. The GUI supports direct command execution, parameter configuration, and drag-and-drop sequence construction to streamline test workflows.

**Technologies Used:** Python, PyQt5, Logging module, Command Parsing, Drag-and-Drop UI

**Key Features:**
- **Command Tab**:  
  - Check firmware versions with simple buttons  
  - Initialize and configure HBot hardware with interactive input  
  - Execute individual HBot commands via dropdown selection  
  - Parameter inputs with default values and session memory of previous inputs  
  - Real-time logging window showing command confirmations and status updates

- **Sequence Builder Tab**:  
  - Drag and drop commands to create custom sequences  
  - Edit parameters of commands via double-click, opening a detailed parameter dialog  
  - Remove commands easily via keyboard shortcuts  
  - Set command repetition counts and run sequences step-by-step  
  - Save and open sequences with keyboard shortcuts (Ctrl+S / Ctrl+O)

- **Modular Command Integration**:  
  - Easily add new commands by defining functions and parameters in backend Python files  
  - Default parameters auto-populate input fields for consistent command execution  
  - Supports both getter and setter style commands with appropriate logging feedback


**GUI Screenshots:**

<table align="center">
  <tr>
    <td style="text-align: center; padding-right: 20px;">
      <img src="../assets/icons/command.png" width="300px" alt="Command Tab">
      <br>
      Command Tab
    </td>
    <td style="text-align: center; padding-left: 20px;">
      <img src="../assets/icons/sequence.png" width="300px" alt="Sequencing Tab">
      <br>
      Sequencing Tab
    </td>
  </tr>
</table>

**GitHub:** [View Repository](https://github.com/cpalencica/SystemUI)

---

## Component Evaluation

**Description:**  
Benchmarked multiple hardware components under standardized test conditions to inform vendor selection and system integration. Evaluated sensors, ADCs, and power regulators for performance, stability, and noise characteristics.

**Technologies Used:** Python, Excel, Multimeter, Oscilloscope, MATLAB, Bench Power Supplies

**Key Features:**
- Created test harness for repeated data acquisition  
- Measured thermal drift, resolution, and startup latency  
- Documented and compared performance across vendors  
- Created summary report with rankings and recommendations

**Hardware Setup:**  
- Breadboard/PCB with interchangeable component sockets  
- Power supply sweep testing  
- Logging via Python and USB-to-UART interface

**Outcome:**  
Informed design decisions for upcoming product revision. Contributed to supplier qualification and BOM optimization.

---
