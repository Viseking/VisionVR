# VisionVR

VisionVR is an open spatial XR platform designed to bring productivity-focused immersive experiences to ordinary VR headsets. The project combines a compatibility layer for common VR hardware with a lightweight spatial workspace and app environment, enabling floating UI, hand/controller input, and passthrough-like overlays.

## Project goals

- Bring immersive spatial computing to mainstream VR headsets
- Provide a comfortable workspace experience for productivity and collaboration
- Support an extensible app and SDK ecosystem
- Validate a practical MVP before expanding into more advanced features

## Repository structure

```text
VisionVR/
├── README.md
├── LICENSE
├── Plan.md
├── docs/
│   ├── README.md
│   ├── product-brief.md
│   ├── requirements.md
│   ├── roadmap.md
│   ├── architecture.md
│   └── research.md
├── hardware/
│   ├── README.md
│   ├── designs/
│   │   └── README.md
│   ├── schematics/
│   │   └── README.md
│   └── BOM/
│       └── README.md
├── software/
│   ├── README.md
│   ├── apps/
│   │   └── README.md
│   ├── core/
│   │   └── README.md
│   ├── sdk/
│   │   └── README.md
│   └── plugins/
│       └── README.md
├── examples/
│   ├── README.md
│   └── demo-apps/
│       └── README.md
├── scripts/
│   ├── README.md
│   ├── setup/
│   │   └── README.md
│   └── build/
│       └── README.md
└── .gitignore
```

## MVP direction

The first milestone focuses on a spatial productivity workstation:

- floating app windows
- app dock and workspace management
- controller or hand input support
- minimal passthrough-like overlay
- custom interaction model for common VR hardware

## Recommended next steps

1. Review the product brief and requirements.
2. Confirm the MVP and supported headset stack.
3. Start prototyping the spatial UI and interaction layer.
4. Validate comfort, usability, and performance with a small test group.

See the `docs/` section for strategy, roadmap, and architecture details.
