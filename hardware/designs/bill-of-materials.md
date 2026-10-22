# Bill of Materials (Prototype)

This is a practical starting BOM for a functional VisionVR prototype.

## Core compute

- Raspberry Pi 5 (recommended)
  - 4GB or 8GB RAM
  - active cooling recommended
- microSD card (64GB or larger)
- USB-C power supply for Pi
- small fan / thermal plate

## Sensor stack

- 2x RGB or global-shutter USB/CSI camera modules
- 1x depth camera (RealSense D435i or a ToF module)
- 1x IR tracking camera for gaze/focus
- 1x 9-axis IMU (BMI088 / MPU6050 / ICM-20948 class)
- 1x power distribution board / regulator
- 1x battery with charger and protection circuit

## Control and IO

- ESP32 development board (WROOM variant)
- GPIO breakout / protoboard
- wiring harness / JST connectors
- buttons / triggers / indicator LEDs

## Mechanical and enclosure

- VR headset shell or mounting frame
- 3D-printed camera brackets
- cable clips and strain relief
- adhesive mounting pads
- optional adjustable front mount for camera alignment

## Optional upgrades

- microphone array
- haptic feedback module
- extra ToF sensor
- wireless USB bridge or Wi-Fi uplink
- secondary compute board for heavier AI tasks

## Estimated prototype cost range

Typical budget range for a working research prototype:

- low end: $200–$400
- medium prototype: $400–$900
- more capable sensor-rich version: $900–$1,800+

The exact cost depends on camera quality, depth sensor choice, and whether the design includes custom enclosure or 3D-printed parts.

## Suggested first BOM

For a first practical build, use:

1. Raspberry Pi 5
2. ESP32 dev board
3. one depth camera
4. one stereo RGB camera pair
5. one IMU
6. one IR eye-tracking camera
7. battery + regulator
8. 3D-printed mounting rig

This provides a strong balance between functionality and prototype complexity.
