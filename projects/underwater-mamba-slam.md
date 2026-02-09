---
title: Underwater MAMBA SLAM
layout: default
parent: Projects
nav_order: 1
project: underwater-mamba-slam
primary_researcher: Waqar Mughal
status: experiments
---

# <Project Title>
{: .no_toc }
A robust, real-time underwater SLAM system that leverages Mamba-based temporal feature extraction and tight fusion of monocular vision with navigational sensors to handle turbidity, low light, and texture-poor scenes.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

- Proposed an underwater SLAM pipeline that uses Mamba’s selective state-space architecture to extract temporally consistent visual features and fuse monocular camera + IMU + DVL data efficiently (linear-time vs. quadratic transformer-style costs), aiming to stay robust under turbidity, low light, and low-texture conditions.
- The system uses a Mamba-based visual front-end for visual odometry, fuses IMU+DVL+compass in an EKF filter for pose/velocity, and performs loop closure using an adapted OverlapMamba embedding/overlap score to correct drift via pose-graph optimization
- Results: On the AQUALOC dataset, it reports lower Absolute Trajectory Error than common baselines while remaining feasible on modest GPU hardware.

## Current Status

**Status:** experiments

**Primary Researcher:** Waqar Mughal

**Start Date:** 


## Goals

- Goal 1
- Goal 2
- Goal 3

## Technical Approach

- **Category 1:** Details
- **Category 2:** Details
- **Category 3:** Details

## Repository

[<repo-name>](<repo-url>)

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
