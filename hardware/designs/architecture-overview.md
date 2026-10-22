# Architecture Overview

## 1. Goal

Build a wearable mixed-reality system that uses a regular VR headset with external computer vision and sensor fusion to enable:

- gesture recognition
- room/environment mapping
- 3D spatial UI placement
- focus and aim tracking
- floating data windows anchored in space

## 2. Recommended hardware split

### Raspberry Pi 5: main intelligence

Use the Raspberry Pi 5 as the primary compute node for:

- OpenCV-based image processing
- hand and gesture recognition
- high-level perception logic
- depth and SLAM processing
- gaze tracking and focus estimation
- control of floating spatial windows and overlays

### ESP32: real-time sensor/control hub

Use the ESP32 for:

- IMU sampling and filtering
- power/battery monitoring
- button and trigger handling
- low-latency telemetry
- communication with Pi via UART, I2C, or Wi-Fi/BLE

## 3. Sensor stack

Recommended minimum prototype stack:

- 2x RGB or global-shutter cameras
- 1x depth sensor (RealSense D435i / Orbbec / ToF)
- 1x 9-axis IMU
- 1x IR camera for eye tracking
- 1x battery monitor and power board
- optional microphone array

## 4. System block diagram

```text
+---------------------------+
|      VR Headset Shell     |
|  Display + optics         |
|  RGB cam 1                |
|  RGB cam 2                |
|  IR eye cam               |
|  IMU + buttons            |
+-------------+-------------+
              |
              | USB-C / CSI / I2C / UART
              v
+---------------------------+
|        ESP32 Hub          |
| - IMU polling             |
| - battery + buttons       |
| - low latency telemetry   |
+-------------+-------------+
              |
              | UART / I2C / Wi-Fi
              v
+---------------------------+
|    Raspberry Pi 5         |
| - gesture recognition     |
| - depth + SLAM            |
| - environment mapping     |
| - gaze / focus tracking   |
| - floating 3D windows     |
+-------------+-------------+
              |
              | HDMI / USB / display output
              v
+---------------------------+
|      Spatial UI / HMD     |
|      overlay + interaction |
+---------------------------+
```

## 5. Perception pipeline

1. Capture frames from RGB + depth + eye tracking camera
2. Synchronize timestamps and align sensor streams
3. Detect hands and estimate pose using MediaPipe or custom CV model
4. Build a room map using depth plus odometry
5. Estimate head pose and gaze vector
6. Fuse camera + IMU for stable spatial awareness
7. Place and update floating 3D windows in room coordinates

## 6. Gesture interaction model

Recommended initial gesture set:

- pinch = select or trigger
- swipe = move between panels or pages
- grab = drag floating window
- palm-open = menu
- fist = close or hide window
- dwell gaze = activate focused item

## 7. Focus and aim tracking

To support focus and aim assistance:

- track pupil position from IR eye camera
- compute gaze direction against display center
- combine gaze direction with head orientation
- raycast into the 3D scene
- identify the active target or focused surface

This creates a practical “look-to-select” and “aim assist” interaction model without requiring full eye-tracking calibration at a production scale.

## 8. Floating window concept

Floating UI objects should be world-anchored rather than screen-fixed. A basic design:

- window has a pose in 3D space
- anchored to room or user position
- can be translated, rotated, and scaled using gestures
- focus can be shaped by gaze dwell or pinch activation
- can snap to walls, desks, or fixed room planes

## 9. Implementation roadmap

### Phase 1 — data acquisition
- camera + IMU streaming
- sensor calibration
- stable output logging

### Phase 2 — perception
- hand tracking
- room depth processing
- basic object detection

### Phase 3 — interaction
- select, drag, and close gestures
- basic floating window movement

### Phase 4 — focus and aim
- gaze detection
- target lock / focus dwell
- pointer and selection assistance

### Phase 5 — prototype refinement
- stability tuning
- latency reduction
- world anchor optimization

## 10. Recommended software stack

- Python + OpenCV
- MediaPipe for hands
- Open3D for 3D scene processing
- PCL or point-cloud utilities for spatial data
- NumPy / SciPy for filtering and transforms
- Raspberry Pi OS + Linux tooling for camera and sensor interfaces

## 11. Best practical design

The strongest initial configuration is:

- Raspberry Pi 5 for compute
- ESP32 for realtime sensor monitoring
- stereo + depth camera stack
- IR eye camera for focus tracking
- room-anchored spatial UI

This is realistic, modular, and scalable for a working prototype without excessive hardware complexity.
