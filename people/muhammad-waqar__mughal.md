---
title: "Muhammad Waqar Mughal"
layout: default
parent: People
nav_order: 1

first_name: Muhammad Waqar
last_name: Mughal
group: phd

honorific_title: 
last_degree: MSCS
public_url:
status: active
offboard: no
research_focus: computer vision, deep learning, underwater robotics, vision, simulation
---

<img src="{{ '/assets/people/waqar.png' | relative_url }}" alt="{{ page.first_name }} {{ page.last_name }}" style="float: left; margin-right: 20px; margin-bottom: 10px; width: 150px;">

# {{ page.first_name }} {{ page.last_name }}
{: .no_toc }

{{ page.research_focus }}
{: .fs-6 .fw-300 }

<div style="clear: both;"></div>

---

## About

- **Background:** Continue PhD in Robotics. Previously worked in University of central Punjab, Lahore, Pakistan as full time lecture in computer sceince department and a part of robotics research center in University.
- **Research Interests:** Testing deep learning models for different type of applications.
- **Current Work:** underwater SLAM using deep learning, underwater simulation
- **Skills:** ROS, Python, C++ and learning many more :).
- **Hobbies:** Badminton, Dance and cooking

<!---
NOTE: DO NOT MODIFY ANYTHING BELOW
-->

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
- [{{ wip.title }}]({{ wip.url | relative_url }})
{% endfor %}
{% else %}
*No WIP entries yet.*
{% endif %}

