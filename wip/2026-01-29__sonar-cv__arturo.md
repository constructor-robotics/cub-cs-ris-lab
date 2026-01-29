---
title: "WIP: sonar-cv - Arturo (2026-01-29)"
layout: default
parent: WIP Log
nav_order: 1
date: 2026-01-29
project: sonar-cv
presenter: Arturo
tags: [computer-vision, sonar, docker, holoocean, simulation]
status: implementing
---

# WIP - Sonar Computer Vision - Arturo - 2026-01-29

## 1) Snapshot (pre-fill)
**Goal (1–2 sentences):**

Develop computer vision algorithms for underwater sonar imagery using the Holoocean simulator to enable autonomous navigation and object detection in simulated marine environments.

**One-line summary of this update:**

Set up Docker environment for Holoocean and successfully rendered first sonar scans with custom camera configurations.

**Links (required)**
- Project page: /projects/sonar-cv/
- Code repo / branch / commit: github.com/lab/sonar-cv / feature/holoocean-setup / a3f7c2d
- Data location + version (path/hash/date): ~/data/sonar-cv/holoocean-v1 / 2026-01-29
- Slides / notes / figures: /lab-drive/sonar-cv/2026-01-29-setup-notes.pdf

**Context for future handover (max 3 bullets)**
- Holoocean requires specific CUDA drivers; Docker container configured with nvidia-docker2
- Base environment uses Holoocean 0.5.2 with custom sonar sensor parameters
- Currently testing with Ocean scene; future work will use Harbor scene for obstacle detection

---

## 2) Since last update: progress & evidence (pre-fill)
**What changed (bullets):**
- Built Docker container with Holoocean dependencies and GPU support
- Configured custom sonar sensor with 512x512 resolution and 90° FOV
- Generated baseline dataset of 100 sonar images from Ocean scene

**Key results (numbers + what they mean):**
- Metric(s): Sonar image generation rate ~15 fps in simulation
- Baseline comparison: Previous PyBullet setup achieved 8 fps
- What improved / regressed (your hypothesis): Better performance due to optimized rendering pipeline in Holoocean

**Artifacts produced (links):**
- Issues: #12 (Docker GPU passthrough), #13 (Sonar parameter tuning)
- Plots: /lab-drive/sonar-cv/sample-renders-2026-01-29.png
- Demo video: N/A (will record next week)

---

## 3) Current approach (make it reproducible)
**Method summary:**
- Problem formulation: Simulate sonar imagery for training object detection models without requiring real underwater data collection
- Approach (algorithm/model/control): Use Holoocean's imaging sonar sensor to generate synthetic training data; will apply YOLOv8 for object detection
- Assumptions / constraints: Simulation accurately represents real sonar characteristics; limited to objects available in Holoocean asset library

**Setup**
- Robot / hardware: Simulated AUV with forward-facing sonar sensor
- Sim / environment version: Holoocean 0.5.2, Ocean scene v1.3, Docker 24.0.7 with CUDA 12.1
