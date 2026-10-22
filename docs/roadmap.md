# Roadmap

## Phase 0 — Foundation and strategy (Days 1–30)

### Objectives

- Confirm the product mission and define the user problem.
- Finalize the MVP: spatial productivity workspace for VR headsets.
- Choose target hardware and platform support.
- Create the project documentation and repository structure.

### Deliverables

- Product brief approved
- MVP scope documented
- Requirements and non-goals defined
- Headset support plan identified
- Initial technical architecture reviewed
- Repo skeleton with docs in place

### Key milestones

- Week 1: define target users and use cases
- Week 2: select support stack (OpenXR, Quest/PCVR-first)
- Week 3: define spatial workspace interactions and UX rules
- Week 4: create technical architecture and backlog

## Phase 1 — Research and prototyping (Days 31–60)

### Objectives

- Validate the prototype concept in a real XR environment.
- Test interaction comfort and workspace usability.
- Confirm the best input model for controllers and/or hand tracking.

### Deliverables

- Floating window prototype
- Workspace layout mockup
- Spatial menu and launch flow
- Controller and hand-tracking input tests
- Basic pass-through overlay concept

### Key milestones

- Week 5: create a minimal XR scene with a dock and floating panels
- Week 6: test pointer and hand-based interaction flows
- Week 7: benchmark frame rate, comfort, and motion sickness risk
- Week 8: refine the UX based on feedback

## Phase 2 — Core software platform (Days 61–90)

### Objectives

- Build the reusable runtime foundation.
- Separate hardware abstraction from user-facing features.
- Prepare for a small demo that shows the real product value.

### Deliverables

- Device abstraction layer
- Input layer for controllers and hand tracking
- Window manager and app docking system
- XR scene runtime
- App lifecycle and workspace state model

### Key milestones

- Week 9: define runtime architecture and module boundaries
- Week 10: implement workspace management and window system
- Week 11: integrate input mapping and gesture handling
- Week 12: create a polished MVP demo and internal validation

## Phase 3 — MVP validation and expansion

### Objectives

- Validate assumptions with users.
- Improve comfort and usability.
- Decide whether to keep the product on a productivity track or expand into collaboration and social use cases.

### Deliverables

- User testing summary
- Usability iterations
- Performance and comfort report
- Recommendation for next expansion phase

## Recommended engineering focus

The project should stay narrow in the first release:

- VR app launcher
- floating workspace windows
- basic spatial desktop layout
- controller or hand interaction support
- passthrough-style overlays for context and comfort

The product should avoid building:

- a full Vision Pro clone
- full-body tracking
- a multi-user social world before product validation
- an overly broad hardware stack before the software layer is proven
