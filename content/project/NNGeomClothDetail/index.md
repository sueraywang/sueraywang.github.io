---
title: Neural Geometry Details for Real-Time Multi-Scale Cloth Simulation
summary: A novel geometric learning framework that bridges the gap between fast coarse cloth simulation and detailed yarn-level dynamics using neural networks and parametric surface reconstruction for real-time applications.

tags:
  - Cloth Simulation
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
Project Proposal

Description of Problem
Current cloth simulation methods face a fundamental trade-off: coarse-resolution simulations achieve real-time performance but lack fine geometric details like yarn-level wrinkles and fabric microstructure, while high-resolution simulations capturing yarn dynamics are computationally prohibitive for interactive applications. Existing wrinkle synthesis techniques add visual detail but often lack physical accuracy and fail to capture the complex mechanical behavior of actual fabric microstructure.

Importance of Problem
Physically accurate, real-time cloth simulation with fine detail is critical for numerous applications including virtual try-on systems, video games, VR/AR environments, digital fashion design, and film production. The ability to simulate yarn-level fabric behavior in real-time would enable more realistic virtual garments and improve the quality of interactive design tools. Moreover, understanding the relationship between coarse-scale dynamics and fine-scale fabric structure has implications for material science and textile engineering.

Proposal
I propose a geometric learning framework that combines state-of-the-art coarse cloth simulation with learned yarn-level dynamics through parametric surface reconstruction. The key insight is that coarse simulation produces locally smooth 2D parametric surfaces that serve as a geometric canvas for fine details.
At coarse level, I take advantages of existing real-time physics simulators (e.g., XPBD, Position-Based Dynamics) for low-resolution cloth mesh. At the fine level, I want to train neural networks to predict yarn-level displacement fields as functions of coarse-level mechanical features (strain tensors, curvature, stretch, etc.) Finally, I can apply a geometric reconstruction thourgh Coons patches or similar parametric surface interpolation to reconstruct high-resolution cloth by composing coarse geometry with learned fine displacements. This creates an efficient pipeline where expensive yarn simulation is replaced by learned predictors operating in the parametric space of the coarse surface and physics is preserved implicitly through the training and interpolation.

Originality
The novelty lies in three key aspects:
Geometric reconstruction framework: Explicitly formulating fine detail prediction as learning displacement fields in parametric patch coordinates, with Coons-based interpolation for C0/C1 continuous reconstruction.
Physics-informed representation: Learning yarn dynamics conditioned on physically meaningful coarse features rather than purely data-driven wrinkle synthesis.
Unified multi-scale approach: Tight integration between classical physics simulation (coarse) and learned mechanics (fine) through a principled geometric interface.
While coarse-to-fine methods and neural cloth simulation exist independently, the combination of parametric surface geometry, physics-informed learning of yarn mechanics, and patch-based reconstruction is novel.

Relationship to Geometric Modeling
This work is fundamentally about geometric modeling at multiple scales. I leverage classical surface representation (parametric patches, ruled surfaces), develop geometric interpolation schemes for multi-resolution reconstruction, and learn mappings between geometric/mechanical features at different scales. The parametric surface framework provides the mathematical structure connecting coarse and fine geometry, making this directly relevant to geometric modeling theory and practice.

List of Goals
First Update will complete literature review covering:
State-of-the-art cloth simulation methods (like PBD, XPBD, FEM-based, etc.).
Neural cloth simulation and learning-based wrinkle synthesis.
Parametric surface reconstruction (like Coons patches, subdivision surfaces, displacement mapping, etc.).
Yarn-level fabric mechanics and multi-scale textile simulation.
If possible, I also want to implement a baseline coarse cloth simulator using existing framework (e.g., XPBD implementation or Position-Based Dynamics).
Second Update will complete the following milestones:
Run high-resolution cloth simulations with yarn-level detail for a simple scenario (like hanging cloth, draping over sphere, etc.) to generate initial training dataset.
Design neural network architecture for predicting yarn displacement fields from coarse features (preliminary design with input/output specifications).
Implement and train initial neural model: Train network to predict fine displacements from coarse mechanical features.
Develop Coons patch reconstruction module: Implement geometric interpolation to reconstruct high-res cloth from coarse mesh and learned displacements.
Preliminary evaluation: Qualitative comparison of reconstructed cloth against ground truth yarn simulation, identify failure cases

Final Submission
Complete an end-to-end pipeline that integrats coarse simulation, learned prediction, and geometric reconstruction running in real-time or near-real-time (Hopefully with an interactive demo showing real-time simulation with learned yarn details).
Perform a quantitative evaluation through:
Geometric error metrics (vertex position error, normal deviation).
Physical plausibility assessment (strain energy comparison).
Performance benchmarks (FPS, inference time breakdown).
If time permits, stretch goal by evaluating the feasibility of generalization across different draping scenarios with the various fabric types or handling challenging cases like sharp folds or self-contact with fine details.
