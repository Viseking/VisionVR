# Requirements

## Product goals

- Support common VR headsets through a device compatibility layer
- Deliver a comfortable spatial workspace for productivity scenarios
- Provide a flexible UI runtime for floating apps and windows
- Enable interaction using controllers and/or hand tracking
- Keep the first version focused and testable

## MVP requirements

### Must-have

- App launcher in VR
- Floating 3D windows
- Basic workspace management
- Controller or hand tracking support
- Minimal passthrough-like overlay
- Basic interaction gestures
- Comfortable scaling and body-position UX
- Stable frame rate and low latency

### Nice-to-have

- Multi-window workspace stacking
- Screen mirroring
- User profiles
- Spatial audio
- Collaboration features

### Non-goals for v1

- full-body tracking
- large-scale multi-user social worlds
- advanced scene reconstruction
- full clone of another vendor ecosystem

## Technical constraints

- The platform should target OpenXR-compatible environments when possible.
- The software stack should support easy iteration during prototype and testing.
- The hardware path must be clearly separated from the software platform in early milestones.

## Acceptance criteria

The project can move into prototype development when:

- the primary target headset is selected
- the MVP experience is defined
- the app runtime and interaction model are documented
- the repo structure is in place for planning and implementation
