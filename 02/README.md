# CS460 Assignment 2: Cube Galaxy (XTK WebGL)

An interactive, multi-dimensional WebGL 3D cube art visualization built with the **XTK (The X Toolkit)** framework, designed from the hand-drawn concept sketch.

---

## 🌌 Visual Design & Architecture

The visualization models a dynamic **"Cube Galaxy"** featuring concentric counter-rotating orbital rings, a pulsating central energy core, and dynamic celestial particle mechanics:

### 1. Central Energy Core
- **Large Central Core Cube**: Anchored at the origin `(0, 0, 0)`, functioning as the galaxy's gravitational and energetic centerpiece.
- **Continuous 3D Tumbling Rotation**: Slowly rotates across all three axes (`rotateX`, `rotateY`, `rotateZ`).
- **Harmonic Scale Breathing**: Pulses rhythmically in scale using orthonormalized 3D transformation matrices to maintain geometric stability without matrix drift.
- **Smooth RGB Color Transition**: Continuously and smoothly shifts between **Azure Blue** $\rightarrow$ **Electric Purple** $\rightarrow$ **Hot Neon Pink** via a three-phase trigonometric interpolation function.

### 2. Radiating Burst Energy Rays
- **32 Radial Energy Particles**: Inspired by the sketch's radiating lines, small voxel cubes stream outward along 3D vectors from the core.
- **Dynamic Color Pulsing**: Alternating vibrant cyan and soft pink rays that travel outward, oscillate, and cycle back to the core.

### 3. Inner Clockwise Orbital Ring
- **8 Smaller Blue Cubes**: Orbit clockwise around the center cube at radius $R = 135$.
- **Curated Cyan/Blue Palette**: Rich shades including Azure Blue, Electric Cyan, Sky Blue, Cobalt, and Ice Blue.
- **3D Tumbling**: Each cube rotates independently around its local axes while orbiting.
- **Visible Orbital Ring**: 30 glowing cyan marker cubes trace the elliptical orbit plane (inclined at $\approx 25^\circ$), faithfully capturing the hand-drawn dashed orbit line.

### 4. Outer Counter-Clockwise Orbital Ring
- **12 Larger Pink/Purple Cubes**: Orbit in the counter-direction (counter-clockwise) at radius $R = 225$.
- **Size Hierarchy**: Dimensioned larger than the inner ring cubes to establish clear spatial depth and visual hierarchy.
- **Curated Magenta/Pink Palette**: Neon Magenta, Hot Pink, Bubblegum, Orchid, Deep Rose, Fuchsia, and Royal Violet.
- **Visible Orbital Ring**: 42 glowing pink/magenta marker cubes trace the outer elliptical trajectory with subtle harmonic wave oscillation.

### 5. Dynamic Outward-Flying & Returning Cubes ("Cosmic Flares")
- **8 Cosmic Flare Cubes**: Periodically launch outward from the inner core and rings into deep space ($R \approx 330 - 450$).
- **Gravitational Trajectory**: Smooth quadratic acceleration (`easeOutQuad`) on the outward flight, followed by smooth cubic deceleration and gravitational return (`easeInOutCubic`) back into the galaxy.
- **Staggered & Synchronized Modes**: Cubes fly outward autonomously on individual schedules, and can also be triggered simultaneously into a galactic flare surge.

### 6. Background Galaxy Starfield
- **55 Scattered Deep-Space Cubes**: Distributed across a wide spherical volume ($R \in [170, 480]$, $Y \in [-180, 180]$) providing parallax and celestial depth.
- **Slow Galactic Drift**: Cubes drift gently around the galactic axis with subtle vertical breathing and independent 3D rotation.

---

## 🎮 Interactive Controls & Shortcuts

| Action | Shortcut | HUD Button | Description |
| :--- | :--- | :--- | :--- |
| **Launch Cosmic Flares** | `Space` | **🚀 Launch Flares** | Sends flare cubes soaring into deep space, then returning |
| **Toggle Auto-Orbit** | `O` | **🔄 Orbit: ON / OFF** | Smooth 360-degree orbital camera rotation |
| **Reset Camera** | `R` | **🎯 Reset** | Resets camera to the default sketch viewing angle |
| **Speed Multiplier** | — | **⚡ Speed: 1.0x / Fast** | Toggles between normal and 1.8x warp speed |
| **Save Scene (JSON)** | `S` | **💾 Save Scene** | Exports scene geometry and camera via `loader.js` |
| **Toggle Sound FX** | `M` | **🔊 Sound: ON / OFF** | Enables/mutes Web Audio synthesis effects |
| **Orbit Camera** | Left-Click + Drag | Mouse Trackball | Rotate camera around center |
| **Pan Camera** | Right-Click + Drag | Mouse Trackball | Pan camera view |
| **Zoom View** | Mouse Scroll Wheel | Mouse Trackball | Zoom in and out |

---

## 📁 Project Files

- **`index.html`**: The final interactive CS460 Assignment 2 visualization implementing the Cube Galaxy.
- **`agent.html`**: Preserved copy of the initial experimental build (kept completely intact).
- **`loader.js`**: CS460 scene serialization (`download()`) and restoration (`upload()`) utility.
- **`README.md`**: Complete documentation, architecture breakdown, and user guide.
