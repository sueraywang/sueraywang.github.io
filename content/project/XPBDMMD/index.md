---
title: Real-time Skirt Simulation of Animated Character with Extended Position Based Dynamics on GPU
summary: I use extended position-based dynamics to implement a real-time cloth simulation on an animated character.

tags:
  - Cloth Simulation
date: '2024-12-10T00:00:00Z'

image:
  caption: A frame from final demo
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: Code
    url_code: ''

---
{{< youtube MuLe-ULOIR8 >}}

This project implements a real-time cloth simulator using extended position-based dynamics (**XPBD**), which reads in cloth mesh data (e.g., .obj files) and anminated character body-proxies data and generates the simulated cloth. 

{{< youtube fuNsNcrQUa8 >}}


Although the simulator works with any cloth mesh and anminated character body-proxies in theory, the result highly depends on the match between proxies and the real body model mesh. Therefore, **_only the skirt_** in the demo is simulated with the XPBD simulator, while the other cloth (the top cloth) is simulated using **Marvelous Designer** for the integrity of visual effects. Below is a list of the key things I accomplished:
- [x] An XPBD cloth simulator that solves naive distance constraints.
- [x] Simple collision detections with the character body using proxies (spheres and cylinders)
- [x] GPU acceleration (I used warp to process the simulation on GPU)
- [x] Used Jacobi solver instead of Gauss-Seidal to resolve the simultaneous read/write issue caused by GPU pro-
cessing.
- [x] Advanced rendering using blender (which involves data manipulation and conversions due to mismatch between
coordinate systems)

Here’s also a list of any items I am expecting to implement in the future:
- [ ] The collision detection/handling with the upper body of human characters due to its complex topology.
- [ ] Cloth’s self collision detection/handling.
- [ ] More intricate constraints for the cloth simulation that would help preserve the cloth’s form (e.g., using angle constraints instead of distance constraints for the bending).