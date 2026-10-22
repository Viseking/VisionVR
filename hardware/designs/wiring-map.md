# Prototype Wiring Map

## 1. Connection overview

This document describes the recommended prototype wiring and physical layout for the VisionVR device.

```text
                   +--------------------+
                   |    VR Headset      |
                   |  Display + optics  |
                   |                    |
                   |  + RGB Cam 1       |
                   |  + RGB Cam 2       |
                   |  + IR Eye Cam      |
                   |  + IMU             |
                   |  + Buttons        |
                   +---------+----------+
                             |
                             | USB-C / CSI / I2C / UART
                             v
                   +--------------------+
                   |      ESP32         |
                   | - IMU reads        |
                   | - battery sensor   |
                   | - button inputs    |
                   | - telemetry out    |
                   +---------+----------+
                             |
                             | UART / I2C / Wi-Fi
                             v
                   +--------------------+
                   | Raspberry Pi 5     |
                   | - camera capture   |
                   | - perception stack |
                   | - SLAM / mapping   |
                   | - gesture logic    |
                   | - focus / aim      |
                   | - spatial UI       |
                   +---------+----------+
                             |
                             | HDMI / USB / display output
                             v
                   +--------------------+
                   |  HMD / overlay     |
                   |  or monitor output |
                   +--------------------+
```

## 2. Signal mapping

### Camera wiring

- RGB camera module(s): connected to Raspberry Pi via CSI or USB
- Depth camera: USB or CSI depending on module support
- IR eye camera: USB or CSI, mounted near display optics

### Sensor wiring

- IMU to ESP32: I2C or SPI
- Buttons and triggers: GPIO input on ESP32
- Battery voltage: ADC input on ESP32
- ESP32 to Pi: UART or Wi-Fi for telemetry

### Power routing

- Pi powered by stable 5V rail or USB-C PD
- ESP32 powered from 3.3V rail or regulated power path
- Depth camera and cameras powered from a clean, stable supply
- Add fuse protection and regulator decoupling in the prototype

## 3. Mechanical layout recommendations

- Mount camera modules at the front of the headset, roughly aligned with the user's forward view
- Mount IR eye camera close to the lens path but shielded from direct light
- Place IMU near the center of mass of the headset mount
- Keep wires routed along the headset frame to avoid obstruction and motion drag

## 4. Prototype reliability notes

- Use twisted pair or shielded cable for IMU lines
- Keep high-noise power leads separate from sensor signal lines
- Add a common ground if using multiple sensor nodes
- Use a compact PCB or wiring harness for clean bench prototypes

## 5. Minimal wiring variant

If you want the simplest prototype:

- Raspberry Pi 5 connected directly to all sensors
- ESP32 only used for IMU, battery, and button handling
- no extra low-level MCU node beyond the ESP32

This reduces complexity while preserving the desired architecture.
