---
layout: page
title: Robot Perception & Control
description: Python | RoboDK | Vision Transformers | Rhino/Grasshopper
img: assets/img/7.jpg
importance: 1
category: robotics
related_publications: false
---

Ongoing work at the **USC Baum Family Maker Space — Advanced Fabrication Lab**, where I build the software layer between design tools and industrial robot arms.

#### Offline simulation and toolpath validation

I design and validate offline simulations and toolpaths for a 6-axis **Stäubli TX60** and a **KUKA KR100P-2** using Rhino, Grasshopper and RoboDK. Running the full program in simulation first catches reach violations, singularities and collisions before anything moves on the shop floor.

#### Real-time control

On top of the offline pipeline, I write Python integration layers that talk to the controllers directly, so programs can be driven online and executed in a closed loop rather than replayed blindly from a pre-generated file.

#### Perception

I train Vision Transformer-based models on live camera feeds so the arm can perceive its workspace in real time and feed that back into planning — the part of the stack that turns a scripted motion into a reactive one.

#### Fabrication automation

Separately, I streamlined the Makerspace's intake and fabrication workflow for 3D-printing work orders across four manufacturing systems (Prusa MK4, Prusa HT90, Formlabs 3L, Stratasys F370), writing Python scripts against the Trello API to automate order processing.
