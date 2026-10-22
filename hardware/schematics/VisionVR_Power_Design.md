# VisionVR Power Design

## Overview

This document defines the electrical architecture for the VisionVR headset at a system level. It is intended to be used as a planning reference while the detailed schematic and PCB capture are developed.

## Power architecture

The headset is designed around a battery-powered architecture with a unified power management unit that distributes power to the compute, display, tracking, and accessory modules.

### Primary power rail

- Battery source: 3.7V nominal Li-ion pack, protected by a battery management and over-current protection path.
- Input rail: 3.3V to 5V rail after PMIC conversion depending on module loading and charger configuration.
- Core domains:
  - 1.8V: memory, low-voltage logic, and signal conditioning
  - 3.3V: MCU, sensor ADCs, and digital interfaces
  - 5V: display backlight, USB-C power path, and accessory bus

### Recommended PMIC flow

1. Battery pack -> reverse polarity protection -> ideal diode / fuse -> PMIC input.
2. PMIC -> one or more buck regulators for 3.3V and 1.8V rails.
3. Dedicated boost converter for display or backlight rail when required.
4. Separate load switch or power gate for sensor and camera modules to enable sleep and power sequencing.

### Key design considerations

- Keep the battery pack close to the PMIC input to minimize voltage drop and improve transient response.
- Route high-current loads away from analog sensor paths and reference clocks.
- Provide separate ground planes or stitching vias for the display and RF sections if the PCB becomes multilayer.
- Use a monitored power down sequence for camera, IMU, and display rails during mode transitions.

## Electrical protection

- TVS diode on external USB-C connector and accessory interfaces
- ESD suppression for sensors and charging contacts
- Resettable fuse / polyfuse on battery and charger paths
- Battery temperature and pack telemetry for verification and safety

## Validation notes

- Confirm charger cutoff and pack current limits with the selected battery vendor.
- Validate peak current draw against the PMIC and inductor ratings under thermal load.
- Measure voltage droop when display, camera, and wireless modules are active simultaneously.

## Next steps

- Replace the high-level PMIC selection with a final part number and schematic values.
- Add rail sequencing and startup timing notes to the formal schematic package.
- Generate a detailed power integrity checklist for prototype testing.
