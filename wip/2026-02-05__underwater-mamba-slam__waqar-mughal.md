---
title: "WIP: underwater-mamba-slam - Waqar Mughal [2026-02-05]"
layout: default
parent: WIP Log
nav_order: 2
date: 2026-02-05
project: underwater-mamba-slam
presenter: Waqar Mughal
tags: [underwater robotics, mapping, localization, simulation, visual odometry]
status: experiments
notetaker: Arturo Gomez-Chavez
---

# WIP - Underwater Mamba SLAM - Waqar Mughal - 2026-02-05

## 1) Snapshot (fill before meeting)
**Project goal (1-3 sentences)**  

- Proposed an underwater SLAM pipeline that uses Mamba’s selective state-space architecture to extract temporally consistent visual features and fuse monocular camera + IMU + DVL data efficiently (linear-time vs. quadratic transformer-style costs), aiming to stay robust under turbidity, low light, and low-texture conditions.
- The system uses a Mamba-based visual front-end for visual odometry, fuses IMU+DVL+compass in an EKF filter for pose/velocity, and performs loop closure using an adapted OverlapMamba embedding/overlap score to correct drift via pose-graph optimization
- Results: On the AQUALOC dataset, it reports lower Absolute Trajectory Error than common baselines while remaining feasible on modest GPU hardware.

**Summary of this update(1–3 sentences)**  

- First time this work is discussed with the overall team, the content for this work was submmited to ICRA 2026
- Explain the research idea and the methods used regarding integrating the MAMBA deep-learning architecture for image feature tracking into underwater mapping/SLAM.
- Discuss the reviews received from ICRA 2026, how to address them and discuss how to follow up the project through puiblications, i.e., conferences/journals  

**Links (required)**
- Project page: [underwater-mamba-slam]({{ '/projects/underwater-mamba-slam/' | relative_url }}) 
- Code repo , branch:  <mark>Missing</mark>
- Data location (version if applicable): <mark>Missing</mark>
- Slides, notes, figures: <mark>Missing</mark>

**Publication and writing (required)**
- Status: writing 
- Link to writing: NA  

---

## 2) Since last update: progress (fill before meeting)
**What changed? (bullets):**
- This first meeting about the project, but the system has been implemented in code, tested with public datasets and a paper to ICRA 2026 was submitted
- Received ICRA reviews (rejection) and decided in which aspects to focus

**Key results (numbers + what they mean)**
- Metric(s):  
- Baseline comparison:  
- What improved / regressed / was constant (your hypothesis)?:  

**Artifacts produced (links if available)**
- Issues:  
- Plots: In the project link
- Demo video: NA

---

## 3) Current approach: let's make it reproducible (fill before meeting)
**Method summary**
- Problem formulation:  
- Approach (algorithm/model/control):  
- Assumptions / constraints:  

**Setup**
- Robot / hardware:  
- Sim / environment version: 
- Other considerations: 

## 4) Feedback & next steps (fill after meeting, except 'Help Needed')

**Help Needed (1-3 bullet points)**
- Help determining which actions to take in order to address ICRA reviewers comments.
- Decide how to best publish the results and progress of this work, target a conference or a journal? both? nad how?

**Discussion-focused elements**
- Questions raised:
  1. Mehtodology was very understandable, so no outstanding questions except those that require more detail explanation for the non-experts in the topic. 
- Suggestions:
  1. It is apparent from observing several ICRA reviews that Abalation studies within the article are becoming a MUST.
    * a) Add processing time (e.g., FPS), if specific hardware is needed to faily obtain this metric, reach out to someone. 
    * b) Need to assess the impact of MAMBA in the pipeline, for replace the MAMBA module with another Transfomer-model to assess the impact
    * c) Report training time when initiating with random weights. Describe the heuristic procesure to initiate with determined weights once some frames/samples have been seen. 
  2. Perhaps the contribution and motivation behind the MAMBA idea for underwater needs to be stressed out more or throughout the paper, as in re-stating that other deep-learning-based methods commonly required large CPU/GPUs to achieve real-time-ness. Such harwdware is hard to deploy in underwater robots/systems, hence MAMBA seems better suited. 
    * a) Based on this, performance in an embedded device could be benefitial.
  3. There is enough material to generate a Journal paper, however, it is worth submitting the current state (incorporating some feedback form reviewers) to a conference and submit all experimation/results to a journal. 
  4. **Future work:**
    * a) Since some observations or images from the enviornments are *always necessary* for the method to perform well, it seems like a nice research topic to perform a systematic study of how many samples, and the diversity between them (vaiance), is needed to achieve good results and generalize.
    * b) Study of performing *quantization* in the MAMBA network in order to achieve better real-time results and be able to deployed in embedded devices. 
- Concerns / risks identified:
  1. Reviewers and research-wise tests in only one dataset are not enough and hardware-wise might be hard to collect ground-truth on a real system.
    * a) Perhaps the most viable option is to focus on well-done simulation. 

**Actions-oriented elements:**
- Decisions made:
  - Focus on realistic and exhaustive simulation (e.g., HoloOcean) to generate diverse datasets as field trials might be hard to organize in a suitable time frame.
  - Run the experiments in robust-enough GPU hardware to collect processing times. 
  - Continue with experiments and addressing reviewers comments to generate content. Then submit a 'minimal' version to a conference and the colection of all results to a journal (journal to be decided later). 
- Next steps:
  - Task 1:
    - Description: Explore HoloOcean to collect datasets and test the MAMBA pipeline
    - Owner: Waqar Mughal
    - Target date: NA
  - Task 2:
    - Description: Rerun experiments in better harsware with enough GPU to collect processing times
    - Owner: Waqar Mughal
    - Target date: NA
  - Task 3:
    - Description: Check availability of field-trial dataset from Italy CNR
    - Owner: Arturo Gomez-Chavez
    - Target date: NA



