---
title: 'The Application of Simplified Strassen Algorithm to Snow Simulation with Material Point Method'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin

date: '2023-10-18T00:00:00Z'
doi: '10.1145/3650215.3650378'

# Schedule page publish date (NOT publication's date).
publishDate: '2024-04-16T00:00:00Z'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In *2023 4th International Conference on Machine Learning and Computer Application*
publication_short: In *ICMLCA 2023*

abstract: As a beautiful yet complicated material, snow and its simulations are significantly challenging in the computer graphics community. Since the introduction of the material point method, abbreviated as MPM, the performance of snow simulations has been augmented in many aspects, including accuracy, stability, and efficiency. Nowadays, researchers work on developing simpler mathematical models or incorporating better hardware design to accelerate the snow simulations, but the overall running speed remains a problem. Instead of improving on the simulation methods, this paper presents a novel approach to optimize the efficiency of snow simulations by applying the simplified Strassen algorithm, an abridgment of a famous fast matrix multiplication algorithm, to snow simulations implemented with MPM. Rather than straightforwardly showing the triumph of the simplified Strassen algorithm over the standard matrix multiplication algorithm in runtime, the results present the evidence that leads to the inference that for simulations with a certain level of disorder, the simplified Strassen algorithm will surpass the standard matrix multiplication algorithm as the simulations progress.

summary: This paper presents a novel approach to optimize the efficiency of snow simulations by applying the simplified Strassen algorithm, an abridgment of a famous fast matrix multiplication algorithm, to snow simulations implemented with MPM.

tags:
  - Physically-based Simulation
  - Computer Graphics
  - Snow Simulation
  - Material Point Method
  - Fast Matrix Multiplication Algorithm

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'papers/SnowSim&Algo.pdf'
url_code: 'https://github.com/sueraywang/snow_modified'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Runtime difference'
  focal_point: ''
  preview_only: false
---
