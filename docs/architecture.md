# Architecture

## High-level system structure

VisionVR is best treated as a layered platform:

### 1. Hardware compatibility layer

Responsible for abstracting headset input, rendering APIs, and device-specific constraints. This layer ensures the platform can work across common VR ecosystems and OpenXR-compatible devices.

### 2. XR experience layer

Handles the spatial workspace, windows, overlays, app docking, interaction metaphors, and motion controls. This is the core user-facing layer of the project.

### 3. Ecosystem layer

Covers SDK, developer tooling, plugins, app packaging, and future support for extension-based features and user-generated experiences.

## Proposed modules

- `software/core` — runtime engine, scene graph, platform services, lifecycle management
- `software/apps` — product-facing experiences and workspace apps
- `software/sdk` — developer interface and integration tools
- `software/plugins` — headset adapters, render drivers, sensors, and extensions
- `hardware` — accessory and compatibility design documents
- `examples` — reference applications and demo modules

## Design principles

- Keep device compatibility abstract and modular.
- Prioritize a small, validated MVP over broad scope.
- Design interactions for comfort, not just novelty.
- Separate product-focused features from experimental research.
