---
title: "WIP: EXAMPLE-sonar-cv - Arturo Gomez-Chavez [2000-01-01]"
layout: default
parent: WIP Log
nav_order: 2
date: 2000-01-01
project: EXAMPLE-sonar-cv
presenter: Arturo Gomez-Chavez
tags: [computer-vision, sonar, docker, holoocean, simulation]
status: concluded
notetaker: Hamza Hussain
---

# WIP - EXAMPLE Sonar Computer Vision - Arturo Gomez-Chavez - 2000-01-01

## 1) Snapshot (fill before meeting)
**Project goal (1-3 sentences)**

- Develop computer vision algorithms for underwater sonar imagery using the Holoocean simulator.
- Enable autonomous navigation and object detection in simulated marine environments.
- Validate detection models in simulation before real-world AUV deployment.

**Summary of this update(1–3 sentences)**

- Set up Docker environment for Holoocean and successfully rendered first sonar scans with custom camera configurations.
- Demonstrated baseline object detection using YOLOv8 on synthetic sonar imagery.
- Achieved 15 fps rendering performance, nearly 2x improvement over previous PyBullet setup.

**Links (required)**
- Project page: [EXAMPLE-sonar-cv]({{ '/projects/EXAMPLE-sonar-cv/' | relative_url }})
- Code repo, branch: [github.com/lab/sonar-cv](https://github.com/lab/sonar-cv) / feature/holoocean-setup
- Data location (version if applicable): ~/data/sonar-cv/holoocean-v1 / 2330-12-12
- Slides, notes, figures: [Teams Link](https://constructoruniversity.sharepoint.com/example-sonar-cv)

**Publication and writing (required)**
- Status: concluded
- Link to writing: [OCEANS 2330 Paper Draft](https://overleaf.com/example-sonar-cv)

---

## 2) Since last update: progress (fill before meeting)
**What changed? (bullets):**
- Built Docker container with Holoocean dependencies and GPU support
- Configured custom sonar sensor with 512x512 resolution and 90 degree FOV
- Generated baseline dataset of 100 sonar images from Ocean scene
- Trained initial YOLOv8 model on synthetic data

**Key results (numbers + what they mean)**
- Metric(s): Sonar image generation rate ~15 fps in simulation; mAP 0.72 on synthetic test set
- Baseline comparison: Previous PyBullet setup achieved 8 fps; no prior detection baseline
- What improved / regressed / was constant (your hypothesis)?: Better performance due to optimized rendering pipeline in Holoocean; detection accuracy limited by domain gap

**Artifacts produced (links if available)**
- Issues: #12 (Docker GPU passthrough), #13 (Sonar parameter tuning), #14 (YOLOv8 integration)
- Plots: /lab-drive/sonar-cv/sample-renders-2330-12-12.png
- Demo video: [YouTube Link](https://youtube.com/example-sonar-demo)

---

## 3) Current approach: let's make it reproducible (fill before meeting)
**Method summary**
- Problem formulation: Simulate sonar imagery for training object detection models without requiring real underwater data collection
- Approach (algorithm/model/control): Use Holoocean's imaging sonar sensor to generate synthetic training data; apply YOLOv8 for object detection with domain adaptation
- Assumptions / constraints: Simulation accurately represents real sonar characteristics; limited to objects available in Holoocean asset library

**Setup**
- Robot / hardware: Simulated AUV with forward-facing sonar sensor
- Sim / environment version: Holoocean 0.5.2, Ocean scene v1.3, Docker 24.0.7 with CUDA 12.1
- Other considerations: Requires NVIDIA GPU with at least 8GB VRAM for real-time rendering

## 4) Feedback & next steps (fill after meeting, except 'Help Needed')

**Help Needed (1-3 bullet points)**
- Guidance on domain adaptation techniques for sim-to-real transfer
- Access to real sonar data for validation

**Discussion-focused elements**
- Questions raised:
  1. How representative is the synthetic sonar noise model compared to real hardware?
  2. What objects should be prioritized for detection in the Harbor scene?
- Suggestions:
  1. Consider using CycleGAN for domain adaptation between synthetic and real sonar
  2. Add more diverse lighting conditions to improve model robustness
  3. Benchmark against existing sonar detection datasets if available
- Concerns / risks identified:
  1. Domain gap between simulation and real sonar may limit real-world performance
  2. Holoocean asset library may not cover all relevant underwater objects

**Actions-oriented elements:**
- Decisions made:
  1. Proceed with Harbor scene for next phase of experiments
  2. Implement domain randomization to improve generalization
- Next steps:
  1. Task 1:
    - Description: Generate 1000-image dataset from Harbor scene with varied conditions
    - Owner: Arturo Gomez-Chavez
    - Target date: 2330-12-20
  2. Task 2:
    - Description: Implement and evaluate CycleGAN domain adaptation
    - Owner: Arturo Gomez-Chavez
    - Target date: 2331-01-15
