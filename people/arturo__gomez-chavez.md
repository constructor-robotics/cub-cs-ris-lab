---
title: "Arturo"
layout: default
parent: People
nav_order: 1

first_name: Arturo
last_name: Gomez Chavez
group: faculty

honorific_title: PhD
last_degree: PhD
public_url:
status: active
offboard: no
research_focus: Computer vision for underwater robotics, sonar imaging, simulation
---

# {{ page.first_name }} {{ page.last_name }}
{: .no_toc }

{{ page.research_focus }}
{: .fs-6 .fw-300 }

---

## About

*Coming soon...*

## Current Projects

{% assign all_projects = site.pages | where_exp: "p", "p.path contains 'projects/'" | where_exp: "p", "p.primary_researcher contains page.first_name and p.primary_researcher contains page.last_name" %}
{% if all_projects.size > 0 %}
{% for project in all_projects %}
- [{{ project.title }}]({{ project.url | relative_url }})
{% endfor %}
{% else %}
*No projects yet.*
{% endif %}

## Related WIP Entries

{% assign person_wips = site.pages | where_exp: "p", "p.path contains 'wip/'" | where_exp: "p", "p.presenter contains page.first_name and p.presenter contains page.last_name" | sort: "date" | reverse %}
{% if person_wips.size > 0 %}
{% for wip in person_wips %}
- [{{ wip.title }}]({{ wip.url | relative_url }}) - {{ wip.date | date: "%Y-%m-%d" }}
{% endfor %}
{% else %}
*No WIP entries yet.*
{% endif %}

