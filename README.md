# Stress Element Analyzer

An interactive web-based tool for analyzing 2D stress states.
It computes principal stresses, maximum shear stress, and visualizes stress transformation through an animated rotating element.

## Overview

This project is a lightweight, browser-based engineering visualization tool designed for students and practitioners working in solid mechanics.

Users can input a general plane stress state:

* Normal stress in x-direction (σx)
* Normal stress in y-direction (σy)
* Shear stress (τxy)

The application then:

* Computes principal stresses (σ₁, σ₂)
* Determines maximum shear stress (τmax)
* Calculates orientation angles
* Animates the stress element as it rotates to key states

## Features

* Real-time stress transformation calculations
* Principal stress determination
* Maximum shear stress evaluation
* Rotation angle computation for:

  * Principal planes
  * Maximum shear planes
* Animated visualization of stress element
* Clear sign convention display
* Interactive UI with step-based visualization:

  1. Original stress state
  2. Principal stress state
  3. Maximum shear state

## Mathematical Basis

The implementation follows classical plane stress transformation equations:

* Average stress:
  σ_avg = (σx + σy) / 2

* Radius of Mohr's Circle:
  R = √[((σx - σy)/2)² + τxy²]

* Principal stresses:
  σ₁,₂ = σ_avg ± R

* Maximum shear stress:
  τ_max = R

* Orientation:
  θₚ = ½ atan(2τxy / (σx - σy))

## Visualization

The canvas-based renderer displays:

* Normal stresses (tension/compression)
* Shear stresses with directional convention
* Rotating stress element
* Real-time stress updates on element faces
* Smooth animated transitions between states

## Sign Convention

* Normal stress:

  * Positive → Tension
  * Negative → Compression

* Shear stress (τxy):

  * Positive → Counter-clockwise tendency
  * Negative → Clockwise tendency

## Usage

1. Enter values for:

   * σx
   * σy
   * τxy
2. Click **"Calculate & Animate"**
3. Use controls to:

   * View original state
   * Rotate to principal stresses
   * Rotate to maximum shear
   * Auto-play the transformation

## Tech Stack

* HTML5
* CSS3
* Vanilla JavaScript (no dependencies)
* Canvas API for rendering

## Project Structure

```
.
├── index.html   # Home Page (UI + logic + rendering)
├── guide.html   # Guide Page (UI + logic + rendering)
├── README.md
├── CONTRIBUTING.md
├── CONTENT_LICENSE.md
└── LICENSE.md
```

## Potential Improvements For Future

* Mohr’s Circle visualization
* Unit system toggle (MPa, psi)
* Export snapshots as images
* Mobile UI optimization
* Support for 3D stress states

## Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for detailed information on how to get started.

## Licensing

This project uses dual licensing:

### Code
Licensed under GNU AGPL v3.0  
→ Applies to all source code, rendering logic, and application behavior

### Educational Content
Licensed under CC BY-NC-SA 4.0  
→ Applies to explanations, guide steps, and instructional material

### What this means

- You can use and modify the code, but must open-source changes if deployed
- You can use the educational material for teaching and learning
- You cannot sell or commercially reuse the educational content

## Contact

For inquiries or collaborations about using the content or the code, reach out to me at kayzspace@outlook.com

---

Code: [GNU AGPL v3.0](LICENSE) | Content: [CC BY-NC-SA 4.0](CONTENT_LICENSE.md)