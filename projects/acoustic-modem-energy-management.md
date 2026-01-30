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

**Status:**
**Primary Researcher:** Hamza Hussain
**Start Date:** December 2025

## Goals

- Write somehting here, bitte
- ..,

## Technical Approach

- Write somehting here, bitte
- ..,
-

## Repository

Example link

## Related WIP Entries

{% assign project_wips = site.pages | where_exp: "item", "item.project == page.project" | sort: "date" | reverse %}
{% if project_wips.size > 0 %}
{% for wip in project_wips %}
- [{{ wip.title }}]({{ wip.url | relative_url }}) - {{ wip.date | date: "%Y-%m-%d" }}
{% endfor %}
{% else %}
*No WIP entries yet.*
{% endif %}
