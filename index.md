---
layout: single
title: "Portfolio"
author_profile: true
---

# Engineering Portfolio

Automation & Robotics Engineer specializing in **mechatronic design, embedded control systems, and manufacturing process engineering** — from CAD/CAM through simulation to working hardware.

---

## Featured Project: 6-DOF Robotic Arm

[GitHub Repository →](https://github.com/wojciechjablonsk1/robotic-arm-6dof)

My engineering thesis project — a complete mechatronic prototype combining mechanical design, embedded programming, electronics, and additive manufacturing.

**Specs**
- 6 degrees of freedom, 7 actuation units
- Control: ESP32 microcontroller + PCA9685 PWM driver, commands sent via Python script
- Analytical inverse kinematics using Denavit–Hartenberg parameters
- Custom C++ control libraries built with a ROS-like architecture
- Currently in performance testing phase

**Contributions**
- Designed the full mechanical structure in SolidWorks, optimized for FDM 3D printing
- Designed and assembled the electronic system
- Implemented control software (ESP32 + C++ + Python)
- Integrated motors, electronics, and control software; tested the prototype

```cpp
bool inverseKinematics(float x, float y, float z,
                        float &theta1, float &theta2, float &theta3) {
    float r = sqrt(x*x + y*y + z*z);
    if (r > (L1 + L2)) return false;

    theta1 = atan2(y, x);

    float cos_t3 = (x*x + y*y + z*z - L1*L1 - L2*L2) / (2.0 * L1 * L2);
    cos_t3 = constrain(cos_t3, -1.0, 1.0);
    theta3 = -acos(cos_t3);

    float alpha = asin(z / r);
    float beta = atan2(L2 * sin(theta3), L1 + L2 * cos(theta3));
    theta2 = alpha + beta;

    return true;
}
```

---

## CAD & Mechanical Design

### Screw Jack
Full mechanical design solving buckling, thread selection, torque analysis, and pedestal wall thickness.

- **Load capacity:** 46,000 N to a height of 300 mm
- **Materials:** C45 screw, B10 nut, EN-GJL-250 body, St3 handle
- **Key calculations:** torque at the main screw connection = 147,683.87 N·mm; friction torque at the collar-insert interface = 77,518.52 N·mm
- **Design features:** free rotation of the collar, dowel-pin connections, body plug, retractable handle, safety factor built into all dimensions

### Reduction Gearbox
Cylindrical gear reducer, sized for a 12 kW / 1,500 rpm input at 1.4 overload factor.

- **Gear ratio:** 3.3
- **Verified service life:** 10,697 h against a 10,000 h requirement
- **Bearings selected:** input 6309 (Cd 53 kN), output 6311 (Cd 71.5 kN)
- **Design features:** dipstick port, oil drain port, keyed shaft connections, sealing provisions, seal-removal access holes

---

## Simulation & FEA

**Welding (thermal/structural FEA)** — Modeled heat source distribution, weld thermal cycle, and resulting deformation.
- Material: S235 steel · Travel speed: 2.4 cm/min · Weld efficiency: 80%
- Peak von Mises stress: 322.85 MPa

**Casting (solidification FEA)** — Analyzed solidification temperature, fill velocity, and shrinkage-defect risk for a casting design.

**CNC machining (Mastercam simulation + FEA)** — Simulated a 5-axis machining center toolpath and validated fixture/workpiece stress under cutting loads.

**Automation (LabVIEW)** — Modeled an automated pneumatic bottle-capping line using three actuators and a vacuum gripper.

---

## Manufacturing Process Engineering

- **Casting:** Mold design and gating system evaluation across multiple parting-line and riser variants
- **Plastics processing:** Selected and specified an injection mold base (Hasco 196×296) for a production part
- **Wire EDM:** Programmed cutting paths (ISO G-code) and post-processor macros for profile machining, achieving Ra 2.8 µm and Ra 1.8 µm surface finishes
- **Process documentation:** Authored CNC operation instruction sheets and welding procedure specifications (WPS) per industry format standards

---

## Programming & Data

- Microcontroller programming on Intel 8080 (assembly, BCD counters) and modern C/C++ (robot control libraries)
- Missing-data approximation using Excel-based statistical methods and VBA macros

---

## Technical Skills

**Programming:** C / C++ · Python · MATLAB · Structured Text (ST), Ladder Diagram (LD), FBD · Assembly (8080/8086)

**Embedded Systems:** ESP32 · Arduino (UNO, Nano) · Raspberry Pi Zero · ESP-IDF · STM32 · Hardware-software integration

**CAD/CAM:** SolidWorks (CSWA certified) · Siemens NX · AutoCAD · Autodesk Inventor · FreeCAD · MasterCAM · SolidCAM · InspireCast

**Simulation:** MATLAB/Simulink · LabVIEW · TwinCAT · Fanuc RoboGuide · Webots · SEE Electrical · Moldex3D · Simufact Welding · OriginLab · Scilab

**Manufacturing Processes:** Casting · Welding · Plastics processing · Additive manufacturing · Abrasive, EDM, and cutting machining

**Tools:** Linux · Windows · Git/GitHub · MS Office · OrcaSlicer · DOSBox

---

## Education

**Warsaw University of Technology**
B.Sc. Automation and Robotisation of Manufacturing Processes · 2022–2026

Main areas of study: robotics, industrial automation, electrical drives of machines and robots, microprocessor systems, additive manufacturing, manufacturing technologies.

---

## Engineering Experience

**MS XTEC GmbH — CNC Machine Operator**
*Trossingen, Germany | August 2023 – September 2023*
- Operated a 5-axis CNC machining center (DMG Mori DMU 105 monoBLOCK)
- Performed dimensional inspection of automotive components using metrology equipment
- Worked with production documentation and ERP systems

**Etisoft Warszawa sp. z o.o. — Engineering Intern**
*Warsaw, Poland | July 2025 – August 2025*
- Supported engineering processes using CAD software (Onshape)
- Used ERP systems for production-related documentation

---

## Scientific & Technical Interests

Robotics · Mechatronics · Embedded systems · Industrial automation · Autonomous & unmanned systems · Additive manufacturing · Robot control systems

---

## Contact

📍 Warsaw, Poland · ✉️ woj.jablo@gmail.com · 🔗 [LinkedIn](YOUR_LINKEDIN) · 🔗 [GitHub](https://github.com/wojciechjablonsk1)

📄 [Download full technical portfolio (PDF)](/assets/PORTFOLIO_TECHNICZNE.pdf)
