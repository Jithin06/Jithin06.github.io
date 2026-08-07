---
layout: page
title: Image-to-STL Converter
description: Python | FastAPI | React | PyTorch | Hugging Face
img: assets/img/12.jpg
importance: 1
category: computer vision
related_publications: false
---

A full-stack local AI pipeline that turns a single 2D photo into a watertight, 3D-printable STL mesh — running entirely on-device, with zero external API cost.

#### How it works

**Depth.** [Depth-Anything-V2](https://github.com/DepthAnything/Depth-Anything-V2) estimates a monocular depth map from the input photo.

**Segmentation.** [SAM (Segment Anything)](https://segment-anything.com/) isolates the object from its background so the mesh is built only from what matters.

**Shape classification.** A geometric classifier scores the mask on circularity, aspect ratio and depth-profile correlation. When the object matches a recognized primitive, the pipeline emits a clean parametric mesh; otherwise it falls back to a bas-relief heightmap generated from the depth map.

#### Stack

A FastAPI backend runs the models and mesh generation; a React frontend handles upload, preview and STL download.
