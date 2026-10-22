# Hardware Schematics

This folder contains the electrical and hardware design assets for the VisionVR project. It is intended to hold the current revision of the high-level schematic references, subsystem interface notes, and the supporting parts and architecture documentation needed for hardware planning and review.

## Purpose

- Capture the system-level hardware architecture for the headset and controller electronics.
- Document the preferred power delivery, sensor, display, and wireless interfaces.
- Provide a reviewable asset set for future schematic capture, BOM refinement, and prototype validation.

## Included design assets

- `VisionVR_Block_Diagram.svg` — system-level hardware block diagram for power, compute, sensing, display, and connectivity.
- `VisionVR_Power_Design.md` — power tree and electrical design notes for the headset electronics.
- `VisionVR_Connector_Map.md` — connector and interface mapping for display, battery, sensor, and accessory signals.
- `VisionVR_BOM.csv` — initial bill of materials for prototype evaluation and sourcing.

## Recommended structure

- `README.md` — overview and design documentation
- `*.svg` / block diagrams — visual architecture references
- `*.md` — electrical notes, interface definitions, and design decisions
- `*.csv` — BOM and parts inventory for early-stage hardware development

## Current scope

The VisionVR hardware concept focuses on a wearable mixed-reality headset with a compact mainboard, battery-backed power management, a high-resolution display path, and a sensor suite suited for gesture tracking, head pose estimation, and wireless connectivity. The assets here are intentionally designed to be architecture-level references that can be upgraded into KiCad or Altium schematic sheets as the design moves from concept to implementation.

## Notes

- Keep design assumptions, constraints, and validation findings in version control.
- Review the power rails and signal integrity assumptions before moving into detailed PCB layout.
- Expand the BOM and connector mapping as the mechanical and electrical revisions become more detailed.

## Suggested next steps

1. Convert the concept block diagram into a full schematic sheet set in KiCad or equivalent CAD tooling.
2. Add a detailed power integrity and thermal analysis section for the display and PMIC rails.
3. Finalize a mechanical-to-electrical interface control document for the visor, battery, and cable assemblies.
