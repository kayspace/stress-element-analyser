# Stress Element Analyzer

An interactive web-based tool for analyzing 2D stress states.
It computes principal stresses, maximum shear stress, and visualizes stress transformation through an animated rotating element, visualizes mohr circle construction.

## Overview

This project is a lightweight, browser-based engineering visualization tool designed for students and practitioners working in solid mechanics.

Users can input a general plane stress state:

- Normal stress in x-direction (σx)
- Normal stress in y-direction (σy)
- Shear stress (τxy)

The application then:

- Computes principal stresses (σ₁, σ₂)
- Determines maximum shear stress (τmax)
- Calculates orientation angles
- Animates the stress element as it rotates to key states
- Also updates both the tranformation and mohr guide for the given data

## Features

- Real-time stress transformation calculations
- Principal stress determination
- Maximum shear stress evaluation
- Rotation angle computation for:
  - Principal planes
  - Maximum shear planes

- Animated visualization of stress element
- Clear sign convention display
- Interactive UI with step-based visualization:
  1. Original stress state
  2. Principal stress state
  3. Maximum shear state

- Step by step full plane transformation guide with animated visualizations

- Step by step full mohr circle drawing guide wih animated visualizations

## How to Use

1. Open `index.html` in your web browser.
2. Enter values for:
   - σx (Normal stress in x-direction, MPa)
   - σy (Normal stress in y-direction, MPa)
   - τxy (Shear stress, MPa)
3. Click **"Calculate & Animate"** to compute and visualize.
4. Use the buttons to switch between views:
   - **1 — Original**: Shows the input stress state.
   - **2 — Principal stresses**: Rotated to eliminate shear.
   - **3 — Max shear**: Rotated to maximum shear orientation.
   - **Auto-play**: Automatically cycles through the transformations.
5. Click **"View Full Plane Transformation Guide"** for detailed explanations.

## Guides

The project includes two guide pages to support both algebraic and graphical learning:

- **[Plane Stress Transformation Guide](guide.html)**: Step-by-step transformation of the stress element, showing how the rotated element reaches the principal and maximum shear states.
- **[Mohr's Circle Guide](mohr_guide.html)**: Graphical construction of Mohr's circle, with centre, radius, principal stress points, and the relation between circle angle and physical rotation.

These guides explain the calculations, how the element rotates, and how Mohr's circle represents the same results.

## Books

The following textbooks were used as reference material while developing this project:

- **Strength of Materials by R.K. Bansal, 6th Edition**
  - [Archive PDF reference](https://ia601904.us.archive.org/24/items/StrengthOfMaterialsByR.K.Bansal/Strength%20of%20Materials%20by%20R.K.Bansal.pdf)
  - [Amazon](https://www.amazon.in/Strength-Materials-S-I-Units-Bansal/dp/B0CZ996YRP/ref=asc_df_B0CZ996YRP?tag=googleshopdes-21&hvadid=709963367270&hvpos=&hvnetw=g&hvrand=2096295048005692090&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9152562&hvtargid=pla-2379953159237&psc=1&hvocijid=2096295048005692090-B0CZ996YRP-&hvexpln=0)
- **Aircraft Structures by David J. Megson, 5th Edition**
  - [Archive PDF reference](https://booksite.elsevier.com/samplechapters/9780080969053/Front_Matter.pdf)
  - [Amazon](https://www.amazon.in/AIRCRAFT-STRUCTURES-ENGINEERING-STUDENTS-2017/dp/9382291059/ref=sr_1_3?crid=2XXEXW8GB0DZL&dib=eyJ2IjoiMSJ9.meMQKFZiAIgYUpW7CGxelBlHmEhqy8qjIsJc5Thz3QGh5XyESWNHGMcVXvWKOnrXJB1k355V4Z2tr_DHx8cROjdqDkqKcNEc4iopi-hguKeAIc7qbyHU1UeiWsSsuuy_Jk7FcLIr4RAT8Sdlww9MsNSFL4hUfbApPArGCRyc9UtWV7-SfHGcy051eOteq_ydXGeTgNog3OjNV0yhhtYps9MZjYF4LULhRywsI3fXLf0.r772gYiw4wW7njGD2DdL53HWgye7lz1QMu2Q-BUjxyA&dib_tag=se&keywords=aircraft+structures&qid=1778771970&s=books&sprefix=aircraft+structure,stripbooks,403&sr=1-3)

## Technicals

### Sign Convention

- Normal stress:
  - Positive → Tension
  - Negative → Compression

- Shear stress (τxy):
  - Positive → Counter-clockwise tendency
  - Negative → Clockwise tendency

### Stress Transformation Equations

- Normal stress on a rotated plane:
  σ_n = (σx + σy) / 2 + (σx - σy) / 2 · cos(2θ) + τxy · sin(2θ)

- Shear stress on a rotated plane:
  τ = -(σx - σy) / 2 · sin(2θ) + τxy · cos(2θ)

- Average stress:
  σ_avg = (σx + σy) / 2

- Radius of the transformation circle:
  R = √[((σx - σy) / 2)² + τxy²]

- Principal stresses:
  σ₁ = σ_avg + R
  σ₂ = σ_avg - R

- Principal plane orientation:
  θₚ = ½ atan(2τxy / (σx - σy))

- Maximum shear orientation:
  θ_s = θₚ ± 45°

### Mohr's Circle Formulas

- Centre of Mohr's circle:
  C = (σx + σy) / 2

- Radius of Mohr's circle:
  R = √[((σx - σy) / 2)² + τxy²]

- Principal stresses from Mohr's circle:
  σ₁ = C + R
  σ₂ = C - R

- Plane coordinates for endpoints:
  A = (σx, τxy)
  B = (σy, -τxy)

- Relation between circle angle and physical rotation:
  2θ on Mohr's circle corresponds to θ in the physical element.

## Visualization

The canvas-based renderer displays:

- Normal stresses (tension/compression)
- Shear stresses with directional convention
- Rotating stress element
- Real-time stress updates on element faces
- Smooth animated transitions between states
- Mohr circle construction states

## Tech Stack

- HTML5
- CSS3
- Vanilla JavaScript (no dependencies)
- Canvas API for rendering

## Project Structure

```
.
├── index.html       # Home Page (UI + logic + rendering)
├── guide.html       # Plane Stress Transformation Guide
├── mohr_guide.html  # Mohr's Circle Guide
├── README.md
├── CONTRIBUTING.md
├── CONTENT_LICENSE.md
└── LICENSE
```

## Potential Improvements For Future

- Add a combined Mohr's circle + rotating element view for side-by-side visualization
- Add alternate τxy sign convention support
- Export computed states and rendered diagrams as images or PDF
- Improve mobile responsiveness and touch controls
- Add input validation and clearer error feedback
- Support unit toggle (MPa / psi) and custom axis labelling
- Add a save/load history of stress cases

## Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for detailed information on how to get started.

## Licensing

This project uses dual licensing:

### Code

Licensed under [GNU AGPL v3.0](LICENSE)
→ Applies to all source code, rendering logic, and application behavior

### Educational Content

Licensed under [CC BY-NC-SA 4.0](LICENSE_CONTENT.md)
→ Applies to explanations, guide steps, and instructional material

### What this means

- You can use and modify the code, but must open-source changes if deployed
- You can use the educational material for teaching and learning
- You cannot sell or commercially reuse the educational content

## Contact

For inquiries or collaborations about using the content or the code, reach out to me at kayzspace@outlook.com

---

Code: [GNU AGPL v3.0](LICENSE) | Content: [CC BY-NC-SA 4.0](CONTENT_LICENSE.md)
