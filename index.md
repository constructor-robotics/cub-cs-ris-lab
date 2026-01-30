---
title: Home
layout: home
nav_order: 1
---

<img src="{{ '/assets/icons/cub-ris-logo-1.jpeg' | relative_url }}" alt="Lab Logo" style="float: left; margin-right: 20px; margin-bottom: 10px; width: 150px;">

# {{ site.lab_name }} - Public Log
{: .no_toc }

This website serves as the public research log and knowledge base for the {{ site.lab_name }}.
{: .fs-6 .fw-300 }

<div style="clear: both;"></div>

---

## About

We document ongoing work-in-progress updates, decisions, and lessons learned so results are easy to track over time and simple for new researchers to pick up.

Each project page links to relevant code, datasets, experiment artifacts, and meeting logs to promote reproducibility and smooth handovers.

By standardizing how we record progress and challenges, the site helps the lab collaborate more effectively and share transferable research practices.

## Team Lead(s) / Principal Investigator(s) (PI)
{% for lead in site.team_leads %}
**[{{ lead.name }}]({{ lead.url }})**{% unless forloop.last %}, {% endunless %}
{% endfor %}

## Quick Links

- [Projects]({{ '/projects/' | relative_url }}) - Summary of all active and past projects
- [WIP Log]({{ '/wip-log/' | relative_url }}) - Latest work-in-progress entries across all projects
- [People]({{ '/people/' | relative_url }}) - Lab members and their contributions
