# Unity + OpenXR Starter Setup

## Recommended stack

For the first practical build, the best path is:

- Unity 3D for XR development
- OpenXR as the abstraction layer
- Meta Quest / PCVR support as target hardware for early validation
- C# for product logic and runtime systems
- Python for tooling, automation, and research scripts

## Project structure for Unity

```text
VisionVR/
├── Assets/
│   ├── Scenes/
│   │   ├── MainWorkspace.unity
│   ├── Scripts/
│   │   ├── Core/
│   │   ├── Interaction/
│   │   ├── UI/
│   │   └── Utilities/
│   ├── Prefabs/
│   ├── Materials/
│   └── XR/
├── Packages/
│   └── manifest.json
├── ProjectSettings/
├── docs/
├── software/
├── hardware/
├── examples/
├── scripts/
└── README.md
```

## Starter Unity setup plan

### 1. Create XR project

- Use Unity LTS version
- Enable the XR Plugin Management package
- Install OpenXR Plugin
- Configure target platform based on current support plan

### 2. Add core runtime modules

- `XRSessionManager` — manages runtime startup and device state
- `WorkspaceController` — handles the central VR workspace layout
- `WindowManager` — creates and arranges floating panels
- `InteractionController` — controllers, pointer, and gesture mapping
- `UIOverlayManager` — lightweight overlay and app launch patterns

### 3. MVP scene layout

Create a single workspace prototype with:

- central virtual desk or launch surface
- floating app windows
- dock or sidebar for app access
- minimal snap and scale interactions
- comfortable bounds and motion rules

### 4. Interaction goals

- support either controller raycasting or hand tracking
- provide a clear visual and audio feedback loop
- reduce fatigue with ergonomic window placement and UI scaling
- keep the first interaction model simple and understandable

## Recommended early deliverables

- launch surface with app icons
- draggable and resizable floating windows
- simple object selection with controller ray
- workspace switching or profile states
- clean user onboarding and calibration flow

## Risks to watch

- poor comfort when the user is forced to look down or reach too often
- excessive motion or latency in window transitions
- inconsistent behavior across target headsets
- too much feature scope before the base workspace is stable

## Recommendation

Use Unity + OpenXR as the starter architecture because it is fast to prototype, familiar for XR workflows, and well-suited to building a spatial productivity workspace without overcommitting to custom low-level rendering or hardware design too early.
