# VisionVR Hardware Designs

This folder contains the initial design package for the VisionVR concept: a wearable VR / mixed-reality prototype that combines a normal VR headset with external computer vision, environmental mapping, and gesture-based interaction.

## Included design files

- [architecture-overview.md](./architecture-overview.md) — overall system concept, sensors, compute split, and interaction model
- [wiring-map.md](./wiring-map.md) — prototype connection map and recommended signal wiring
- [bill-of-materials.md](./bill-of-materials.md) — suggested BOM for an initial prototype build
- [visionvr-system-overview.svg](./visionvr-system-overview.svg) — high-level system architecture illustration
- [visionvr-wiring-map.svg](./visionvr-wiring-map.svg) — wiring / connection map illustration

## Concept summary

The recommended platform is:

- Raspberry Pi 5 as the main compute engine for vision, mapping, gesture recognition, and spatial UI generation
- ESP32 as a low-latency sensor/control hub for IMU, buttons, battery telemetry, and peripheral IO
- Depth camera plus stereo RGB / IR cameras for room mapping and hand tracking
- Eye-tracking camera for gaze/focus detection and aiming assistance
- 3D floating window system anchored to the room or user position

This folder is intended to be the starting point for hardware and software design exploration for the prototype.
