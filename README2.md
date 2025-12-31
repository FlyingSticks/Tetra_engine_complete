# Tetrahedral Engine: X-Slit Light Field Visualization

## Overview
The **Tetrahedral Engine** is a browser-based, interactive simulation of General Linear Camera (GLC) geometry. Specifically, it models an **X-Slit (Cross-Slit) projection system**, where the vertical and horizontal apertures are decoupled and placed at different depths along the Z-axis.

Unlike a standard pinhole camera which forces all light rays to converge at a single point, this engine generates a **ruled surface** of light rays. This allows for unique anamorphic properties where aspect ratio, focus, and distortion can be manipulated independently for the X and Y axes.

## Live Demo
> **[View the Live Simulation Here]([https://(flyingsticks.github.io/tetrahedral-engine/](https://flyingsticks.github.io/Tetra_engine_complete/))**
*(Note: Ensure this link matches your specific repository URL)*

## Key Features
* **Decoupled Aperture Control:** Manipulate the Z-depth of the Vertical (Blue) and Horizontal (Green) slits independently to alter the light field topology.
* **Ruled Surface Visualization:** A "High-Density Field" toggle renders 80+ ray traces to visualize the twisting "tetrahedral" shape of the light field between the apertures.
* **Real-Time Telemetry:** Dynamic calculation of the projected Aspect Ratio based on current slit positions.
* **Hardware Visualization:** Explicit rendering of the Sensor plane, Aperture planes, and the Target Object.

## Controls
The simulation provides a control panel for the following parameters:

| Control | Color Code | Description |
| :--- | :--- | :--- |
| **Object Z-Position** | 🔴 Red | The depth of the target subject (Source). |
| **Vertical Slit** | 🔵 Blue | The aperture controlling horizontal scaling/convergence. |
| **Horizontal Slit** | 🟢 Green | The aperture controlling vertical scaling/convergence. |
| **Sensor Position** | ⚪ White | The depth of the projection plane (Image Plane). |

## Technical Implementation
* **Core Logic:** The engine calculates ray trajectories using independent slope intercepts for the X and Y axes.
    * `mx = -x / (Z_v - Z_obj)`
    * `my = -y / (Z_h - Z_obj)`
* **Rendering:** 3D visualization is handled via **Plotly.js**, utilizing a Z-sort algorithm to ensure correct occlusion handling regardless of component order.
* **Stack:** Vanilla HTML5 / JavaScript (ES6).

## Development Roadmap
* [ ] Integration of Lorentz transformations to simulate relativistic effects.
* [ ] Texture mapping for the target object (replacing wireframe).
* [ ] Export functionality for calculated projection matrices.

## License
Copyright © 2025 flyingsticks. All Rights Reserved.
