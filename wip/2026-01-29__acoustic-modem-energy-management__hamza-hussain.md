---
title: "WIP: acoustic-model-energy-management - Hamza Hussain [2026-01-29]"
layout: default
parent: WIP Log
nav_order: 1
date: 2026-01-29
project: acoustic-modem-energy-management
presenter: Hamza Hussain
tags: [underwater robotics, navigation, localization, simulation, acousti communication]
status: experiments
notetaker: Arturo Gomez-Chavez
---

# WIP - Acoustic Model Energy Management - Hamza Hussain - 2026-01-29

## 1) Snapshot (fill before meeting)
**Project goal (1-3 sentences)**  

- Project aimed to study an adaptive acoustic beacon (modem) management method for USV-AUV localization.
- Reduce acoustic communication energy consumption during AUV localization by turning acoustics off or using fewer beacons when possible.
- Preserve mission-defined limits on localization uncertainty/accuracy
- Fincish OCEANS submitted paper and possible extend work for another publication 

**Summary of this update(1–3 sentences)**  

- First time work is discussed with the overall team, the abstract for this work was submmited to OCEANS 2026
- Explain the research idea and the methods used regarding localization, acosutic communication, onbservability/information (e.g. Fisher info), battery state-of-charge (SOC), etc.
- Show the results obtained from Holoocean simulator and discuss the implementation.  

**Links (required)**
- Project page: [acoustic-modem-energy-management]({{ '/projects/acoustic-modem-energy-management/' | relative_url }}) 
- Code repo , branch:  [GitHub Link](https://github.com/hamzahussain5500/holodev_acoustic_manager)
- Data location (version if applicable): <mark>Missing</mark>
- Slides, notes, figures: [Teams Link](https://constructoruniversity.sharepoint.com/:f:/r/sites/HumanoidRobots/Shared%20Documents/General/Projects/acoustic-modem-energy-management?csf=1&web=1&e=YW74og)

**Publication and writing (required)**
- Status: writing 
- Link to writing: NA  

---

## 2) Since last update: progress (fill before meeting)
**What changed? (bullets):**
- Frame the final idea for the research project
-  Develop all the experiments in Holoocean simulator
- Write the abstract for OCEANS 2026

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
- Where to focus the research next? The system was fully implemented in simulation but there are many areas where one can focus and study their behavior, e.g. localization filters, 
- Decide how and where to limit the research to complete the OCEANS paper and then possibly use the rest of the results for another paper 

**Discussion-focused elements**
- Questions raised:
  1. What are the limits and constrains of your experiments/setup? e.g, Velocity of the vehicle, fix localization of USVs
  2. How are the weights for the Adaptive Score chosen? For more strict publications arbitrarily chosen weights might concern reviewers
- Suggestions:
  1. Important parameters of the simulation have to be obtained or addressed, to see if they make "real-life" sense. 
  2. a) Justify weights from mission parameters, or derived from max thresholds in RMSE and Energy b) Find systematicaly 'good' weights by evaluating across many trajectories, beacons geometries, noise, etc (although will require a lot of simulation). 
  3. To extend the work and prove relevancy, think about downstream applications that can be benefited from this. For example, SLAM can be imporved with better acoustic localization or mission planning. Perhaps the next paper is in this direction. 
  4. The presenter mentioned that the method proves to be very benefitial when there is no depth sensor involved, this seems like a good jsutification for the method. 
  5. Remember to include ablation studies in case of a longer paper.
- Concerns / risks identified:
  1. Not critical, but this would be hard to reproduce with physical robots as there is not enough hardware material for this. 

**Actions-oriented elements:**
- Decisions made:
  - Verify simulation parameters are feasible in real-world scenarios, e.g., UAV velocity
  - Explore and decide in which area to deep-dive in order to highlight the relevancy of the work, e.g., performance without depth sensor, noise in the acoustics, etc. 
- Next steps:
  - Task 1:
    - Description: Verify simulation parameters are feasible in real-world scenarios, e.g., UAV velocity, range, etc
    - Owner: Hamza Hussain
    - Target date: NA
  - Task 2:
    - Description: Explore and decide in which area to deep-dive in order to highlight the relevancy of the work
    - Owner: Hamza Hussain
    - Target date: NA



