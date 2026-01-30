---
title: Projects
layout: default
nav_order: 3
has_toc: false
---

# Projects
{: .no_toc }

This page contains a summary of all research projects in the lab.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

Each project maintains its own dedicated page with documentation, links to code repositories, datasets, and related WIP entries. Projects follow a consistent structure to facilitate collaboration and knowledge transfer.

{% assign projects = site.pages | where_exp: "page", "page.path contains 'projects/'" | where_exp: "page", "page.name != 'TEMPLATE.md'" | where_exp: "page", "page.project" %}

## Active Projects

{% assign active_projects = projects | where_exp: "page", "page.status != 'concluded'" | sort: "title" %}
{% if active_projects.size > 0 %}
{% for project in active_projects %}
### [{{ project.title }}]({{ project.url | relative_url }})

**Primary Researcher:** {{ project.primary_researcher }}
**Status:** {{ project.status }}

{% endfor %}
{% else %}
*No active projects yet.*
{% endif %}

## Past Projects

{% assign past_projects = projects | where_exp: "page", "page.status == 'concluded'" | sort: "title" %}
{% if past_projects.size > 0 %}
{% for project in past_projects %}
### [{{ project.title }}]({{ project.url | relative_url }})

**Primary Researcher:** {{ project.primary_researcher }}
**Status:** {{ project.status }}

{% endfor %}
{% else %}
*No past projects yet.*
{% endif %}
