---
title: "Arturo Gomez Chavez"
layout: default
parent: People
nav_order: 1

first_name: Arturo
last_name: Gomez-Chavez
group: faculty

honorific_title: PhD
last_degree: PhD
public_url:
status: active
offboard: no
research_focus: computer vision, deep learning, underwater robotics, sonar, stereo, simulation
---

# {{ page.first_name }} {{ page.last_name }}
{: .no_toc }

{{ page.research_focus }}
{: .fs-6 .fw-300 }

---

## About

- **Background:** Finished PhD in Robotics in December 2025. Previously worked in Copmuter Vision for Waste Management as team-lead and co-founder.
- **Research Interests:** Multimodal models (with different sensor modalities not only text+vision). Production AI-Agents
- **Current Work:** Sonar reconstruction, underwater simulation
- **Skills:** Good at many, expert of nothing =P Docker, ROS, Backend, etc. Python, C++. 
- **Hobbies:** Semi-retired and old martial artist, fan of dogs and anime when it was not mainstream

### {{ page.first_name }} in an image
![Arturo]({{ '/assets/people/arturo-gomez-chavez.png' | relative_url }})

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

