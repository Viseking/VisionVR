# VisionVR Connector Map

## Interface summary

This document maps the principal electrical interfaces that the VisionVR hardware concept uses to connect display, power, sensors, and accessories.

## Main functional interfaces

| Interface | Description | Typical voltage / signaling | Notes |
| --- | --- | --- | --- |
| Battery Pack | Main energy source for the headset | 3.7V nominal; protected path | Managed through PMIC and safety circuitry |
| USB-C | Charging and host connection | 5V, USB 2.0/3.x, DP alt mode optional | Use ESD and TVS protection |
| Display FPC | Panel interface to mainboard | MIPI DSI / LVDS / parallel | Keep high-speed traces short and matched |
| Camera FPC | Vision sensor assembly | MIPI CSI or parallel camera interface | Use impedance-controlled routing |
| IMU / Sensor Flex | Tracking and orientation sensors | I2C / SPI / analog | Place near sensor cluster |
| Audio Flex | Speaker and microphone lines | I2C / analog audio / PWM | Ensure EMI isolation |
| Wireless Module | Wi-Fi / Bluetooth / RF front-end | 3.3V + RF signals | Keep antenna area clear of metal |
| Accessory Port | Expansion, controllers, and external modules | 5V / GPIO / I2C / UART | Add electrostatic protection |

## Recommended connector strategy

- Use a compact USB-C connector for charging and data.
- Prefer board-to-board or flex connectors for display and sensor assemblies.
- Keep high-speed interface traces away from the battery and power switching nodes.
- Reserve additional pinout space for debug, thermal sensors, and future feature expansion.

## Signal grouping guidance

- Analog sensor and RF sections should remain isolated from the PMIC switching node.
- Display and camera interfaces should be grouped and routed with controlled length matching.
- Power and ground pins should be separated from low-noise signal pins on the connector breakout.

## Review checklist

- Verify mechanical fit between the folded visor assembly and the FPC lengths.
- Validate connector pitch against available enclosure features.
- Confirm that accessory and charging connectors do not interfere with the headband or battery module.
