---
title: "Hamza Hussain"
layout: default
parent: People
nav_order: 2

first_name: Hamza
last_name: Hussain
group: masters

honorific_title:
last_degree: Bachelors
public_url:
status: active
offboard: no
research_focus:
---

# {{ page.first_name }} {{ page.last_name }}
{: .no_toc }

{{ page.research_focus }}
{: .fs-6 .fw-300 }

---

## About

*Coming soon...*

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

{% assign person_wips = site.pages | where_exp: "p", "p.path contains 'wip/'" | where_exp: "p", "p.presenter contains page.first_name and p.presenter contains page.last_name" | sort: "date" | reverse %}
{% if person_wips.size > 0 %}
{% for wip in person_wips %}
- [{{ wip.title }}]({{ wip.url | relative_url }}) - {{ wip.date | date: "%Y-%m-%d" }}
{% endfor %}
{% else %}
*No WIP entries yet.*
{% endif %}
