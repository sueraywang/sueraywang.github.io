---
title: Real-Time Skirt Simulation with Extended Position Based Dynamics on GPU
summary: Real-time cloth simulation on animated characters using Extended Position-Based Dynamics (XPBD) with GPU acceleration.

tags:
  - Cloth Simulation
  - Physically-based Simulation
  - Computer Graphics
  - Position Based Dynamics
date: '2024-12-10T00:00:00Z'

image:
  caption: A frame from final demo
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: Code
    url_code: ''

authors:
  - admin

---

## Overview

This project implements a real-time cloth simulator using **Extended Position-Based Dynamics (XPBD)** on GPU. The system reads cloth mesh data (e.g., .obj files) and animated character body-proxy data to generate physically simulated cloth in real-time.

{{< youtube MuLe-ULOIR8 >}}

---

## Technical Details

The simulator works with arbitrary cloth meshes and animated character body-proxies. However, simulation quality depends heavily on the match between proxies and the actual body model mesh. 

**Note:** In the demo, only the **skirt** is simulated using the XPBD simulator. The top cloth is simulated using **Marvelous Designer** for visual consistency.

{{< youtube fuNsNcrQUa8 >}}

---

## Implementation Features

### Completed Features
- XPBD cloth simulator with distance constraints
- Collision detection with character body using proxy geometry (spheres and cylinders)
- GPU acceleration using NVIDIA Warp
- Jacobi solver implementation (resolves simultaneous read/write issues in GPU processing)
- Advanced rendering in Blender with coordinate system alignment

### Future Enhancements
- Collision detection/handling with complex upper body topology
- Cloth self-collision detection and resolution
- Advanced constraints for better form preservation (e.g., angle constraints for bending)

---

## Technical Approach

**Physics Simulation:** Extended Position-Based Dynamics provides stable, real-time simulation with constraint-based solving.

**GPU Acceleration:** Implemented using NVIDIA Warp for parallel constraint solving. The Jacobi solver ensures thread-safe updates during parallel processing.

**Collision Handling:** Simple proxy-based collision detection using sphere and cylinder primitives for real-time performance.

**Rendering Pipeline:** Data exported to Blender with careful coordinate system transformations for high-quality visualization.