---
title: Neural Geometry Details for Real-Time Multi-Scale Cloth Simulation
summary: A geometric learning framework that bridges fast coarse cloth simulation and detailed yarn-level dynamics using neural networks and parametric surface reconstruction.

tags:
  - Cloth Simulation
  - Physically-based Simulation
  - Geometric Modeling
  - Deep Learning
date: '2024-10-09T00:00:00Z'

# image:
#   caption: Neural cloth simulation with yarn-level detail reconstruction
#   focal_point: Smart
#   filename: featured.png

links:
  - icon: github
    icon_pack: fab
    name: Code
    url_code: ''

authors:
  - admin

---

## Overview

This project develops a multi-scale cloth simulation approach that combines real-time coarse physics simulation with learned yarn-level geometric details. By training neural networks to predict fine-scale displacement fields and reconstructing them using parametric surface patches, we achieve physically plausible cloth with yarn-level detail at interactive frame rates.

---

<details>
<summary><strong>Project Proposal</strong></summary>

### Problem Statement

Current cloth simulation methods face a fundamental trade-off between performance and detail:

- **Coarse-resolution simulations** achieve real-time performance but lack fine geometric details like yarn-level wrinkles and fabric microstructure
- **High-resolution simulations** capturing yarn dynamics are computationally prohibitive for interactive applications  
- **Existing wrinkle synthesis techniques** add visual detail but often lack physical accuracy and fail to capture complex mechanical behavior of fabric microstructure

### Motivation

Physically accurate, real-time cloth simulation with fine detail is critical for:

- Virtual try-on systems and digital fashion design
- Video games and VR/AR environments
- Film production and visual effects
- Material science and textile engineering research

The ability to simulate yarn-level fabric behavior in real-time would enable more realistic virtual garments and improve the quality of interactive design tools.

---

### Proposed Approach

A three-level geometric learning framework combining coarse physics simulation with learned yarn-level dynamics:

- **Coarse Level:** Leverage existing real-time physics simulators (XPBD, Position-Based Dynamics) for low-resolution cloth mesh
- **Fine Level:** Train neural networks to predict yarn-level displacement fields as functions of coarse mechanical features (strain tensors, curvature, stretch)
- **Reconstruction Level:** Apply parametric surface interpolation (Coons patches) to reconstruct high-resolution cloth by composing coarse geometry with learned fine displacements

**Key Insight:** Coarse simulation produces locally smooth 2D parametric surfaces that serve as a geometric canvas for fine details, enabling efficient learned detail synthesis while preserving physics.

---

### Novelty

- **Geometric reconstruction framework:** Formulating fine detail prediction as learning displacement fields in parametric patch coordinates with Coons-based C0/C1 continuous reconstruction
- **Physics-informed representation:** Learning yarn dynamics conditioned on physically meaningful coarse features rather than purely data-driven synthesis
- **Unified multi-scale approach:** Tight integration between classical physics simulation and learned mechanics through principled geometric interface

---

### Relationship to Geometric Modeling

This work fundamentally addresses geometric modeling at multiple scales by:

- Leveraging classical surface representations (parametric patches, ruled surfaces)
- Developing geometric interpolation schemes for multi-resolution reconstruction
- Learning mappings between geometric and mechanical features at different scales

The parametric surface framework provides the mathematical structure connecting coarse and fine geometry.

---

### Project Milestones

**Phase 1: Foundation & Literature Review**

- Survey state-of-the-art cloth simulation methods (PBD, XPBD, FEM-based)
- Review neural cloth simulation and learning-based wrinkle synthesis
- Study parametric surface reconstruction techniques (Coons patches, subdivision surfaces, displacement mapping)
- Research yarn-level fabric mechanics and multi-scale textile simulation
- Implement baseline coarse cloth simulator using existing framework

**Phase 2: Core Development**

- Generate training dataset: High-resolution yarn-level cloth simulations (hanging cloth, draping scenarios)
- Design neural architecture for predicting yarn displacement fields from coarse features
- Implement and train initial model
- Develop Coons patch reconstruction module for geometric interpolation
- Perform preliminary qualitative evaluation against ground truth

**Phase 3: Integration & Evaluation**

- Complete end-to-end pipeline integrating coarse simulation, learned prediction, and geometric reconstruction
- Achieve real-time or near-real-time performance
- Develop interactive demo
- Quantitative evaluation:
  - Geometric error metrics (vertex position error, normal deviation)
  - Physical plausibility (strain energy comparison)
  - Performance benchmarks (FPS, inference time)

**Stretch Goals**

- Generalization across different draping scenarios and fabric types
- Handle challenging cases (sharp folds, self-contact with fine details)

</details>
