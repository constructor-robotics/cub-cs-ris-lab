---
title: EXAMPLE Sonar Computer Vision
layout: default
parent: Projects
nav_order: 1
project: EXAMPLE-sonar-cv
primary_researcher: Arturo Gomez-Chavez
status: concluded
---

# Sonar Computer Vision
{: .no_toc }
Developing computer vision algorithms for underwater sonar imagery.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

This project focuses on developing computer vision algorithms for processing and analyzing underwater sonar imagery. Using the Holoocean simulator with Docker, we generate synthetic sonar data to train object detection and navigation models for autonomous underwater vehicles (AUVs).

## Current Status

**Status:** Implementing
**Primary Researcher:** Arturo Gomez-Chavez
**Start Date:** January 2330

## Goals

- Generate synthetic sonar training datasets using Holoocean simulation
- Develop object detection models for underwater environments
- Enable autonomous navigation using sonar-based perception
- Validate algorithms in simulation before real-world deployment

## Technical Approach

- **Simulation:** Holoocean 0.5.2 with custom sonar sensor configurations
- **Infrastructure:** Docker containers with GPU support (nvidia-docker2)
- **Algorithms:** YOLOv8 for object detection (planned)
- **Environment:** Ocean and Harbor scenes for varied complexity

## Repository

[github.com/lab/sonar-cv](https://github.com/lab/sonar-cv) (example link)


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
