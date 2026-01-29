---
# Person Template - Copy this file and rename to: firstname__lastname.md
title: "Firstname Lastname"
layout: default
parent: People
nav_order: 1

# Required fields
first_name: Firstname
last_name: Lastname
group: faculty  # Options: faculty, phd, masters, undergrad, external

# Optional fields
honorific_title:      # e.g., Dr., Prof.
last_degree:          # e.g., PhD, MSc, BSc
public_url:           # Personal website or profile URL
status: active        # active / inactive
offboard: no          # yes / no
research_focus:       # Brief description of research interests
---

# {{ page.honorific_title }} {{ page.first_name }} {{ page.last_name }}
{: .no_toc }

{{ page.research_focus }}
{: .fs-6 .fw-300 }

---

## About

*Add bio here...*

## Current Projects

{% assign all_projects = site.pages | where_exp: "p", "p.path contains 'projects/'" | where_exp: "p", "p.primary_researcher == page.first_name" %}
{% if all_projects.size > 0 %}
{% for project in all_projects %}
- [{{ project.title }}]({{ project.url | relative_url }})
{% endfor %}
{% else %}
*No projects yet.*
{% endif %}

## Related WIP Entries

{% assign person_wips = site.pages | where_exp: "p", "p.path contains 'wip/'" | where_exp: "p", "p.presenter == page.first_name or p.presenter contains page.first_name" | sort: "date" | reverse %}
{% if person_wips.size > 0 %}
{% for wip in person_wips %}
- [{{ wip.title }}]({{ wip.url | relative_url }}) - {{ wip.date | date: "%Y-%m-%d" }}
{% endfor %}
{% else %}
*No WIP entries yet.*
{% endif %}
