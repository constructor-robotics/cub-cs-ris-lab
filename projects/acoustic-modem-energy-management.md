---
title: Acoustic Modem Energy Management
layout: default
parent: Projects
nav_order: 1
project: acoustic-modem-energy-management
primary_researcher: Hamza Hussain
status: experiments
---

# Acoustic Model Energy Management
{: .no_toc }
Reduce acoustic communication/ranging energy consumption during AUV localization
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

Reduce acoustic communication/ranging energy consumption during AUV localization by turning acoustics off or using fewer beacons when possible, while still maintaining mission-defined limits on localization uncertainty/accuracy.

## Current Status

**Status:** Work in Progress
**Primary Researcher:** Hamza Hussain
**Start Date:** December 2025

## Goals

The goal is to explore the energy conservation in acoustic localisation schemes by dynmaically selecting modem arrays(in an SBL-like setup) and use their ranges in an EKF based on energy, uncertainty, and mission constraints,in AUV-USV collaborative tasks.
- ...

## Technical Approach

* **Problem:** Maintain reliable USV–AUV localization when underwater acoustic links are intermittent and energy-limited, while still meeting mission accuracy needs.

* **Simulation & Data:** Run repeatable missions in **HoloOcean** with multiple acoustic beacons/modems (used ranges from USBL modems in 4 vehicles in a tetrahedron shape), generating ground truth, IMU, DVL velocity, depth, and acoustic range measurements. Test multiple trajectories (e.g., lawnmower, spiral/descending spiral, figure-8).

* **State Estimation (Fusion):** Use an **Extended Kalman Filter (EKF)** to fuse:

  * **IMU-driven prediction** (motion model + process noise),
  * **DVL update** for velocity in world frame,
  * **Depth update** for (z),
  * **Acoustic range updates** from available beacons with innovation gating (NIS) to reject outliers.

* **Observability & Geometry Scoring:** Evaluate candidate beacon subsets using **range Jacobians** (H) and the **Fisher Information Matrix**
  [
  F = H^\top R^{-1} H
  ]
  and derive geometry metrics (rank, log-det, GDOP, CRLB). Compute both:

  * **3D geometry** (xyz),
  * **2D horizontal geometry** (xy) when depth is reliably measured.

* **Energy Awareness (SOC):** Model **battery state-of-charge (SOC)** and penalize beacon selections that increase acoustic energy usage, enabling accuracy–endurance trade-offs.

* **Mission Uncertainty Objective:** Predict how each candidate subset would reduce estimation uncertainty using a **posterior covariance approximation**, and choose the subset that best meets mission accuracy with minimal energy:
  [
  P^+(S) \approx \left(P^{-^{-1}} + H(S)^\top R^{-1}H(S)\right)^{-1}
  ]

* **Robustness Testing:** Stress-test the system using scripted **modem dropout schedules** (single and overlapping outages). Report performance via position error statistics, uncertainty proxy (\sqrt{\mathrm{trace}(P_{pos})}), and consistency metrics (NEES/NIS).

* **Outputs:** Produce paper-ready plots and tables for error, uncertainty, geometry (log-det/GDOP/CRLB), and dropout-phase comparisons, supporting a clear link between **beacon selection**, **observability**, **energy**, and **localization accuracy**.

## Repository

[GitHub Link](https://github.com/hamzahussain5500/holodev_acoustic_manager)

<!---
NOTE: DO NOT MODIFY ANYTHING BELOW
-->

## Related WIP Entries

{% assign project_wips = site.pages | where_exp: "item", "item.path contains 'wip/'" | where_exp: "item", "item.project == page.project" | sort: "date" | reverse %}
{% if project_wips.size > 0 %}
{% for wip in project_wips %}
- [{{ wip.title }}]({{ wip.url | relative_url }})
{% endfor %}
{% else %}
*No WIP entries yet.*
{% endif %}
