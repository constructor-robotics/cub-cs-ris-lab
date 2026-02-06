---
title: <Project Title>
layout: default
parent: Projects
nav_order: 1
project: <project-slug>
primary_researcher: <Full Name>
status: exploring | implementing | experiments | writing | wrapping-up | maintenance | concluded
published: False
---
<!---
Please don't inlicde the published Tag above when creating your file
-->

# <Project Title>
{: .no_toc }
<One-line project description>
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

<2-4 sentence description of the project, its goals, and significance.>

## Current Status

**Status:** <exploring | implementing | experiments | writing | wrapping-up | maintenance | concluded>
**Primary Researcher:** <Full Name>
**Start Date:** <Month Year>

## Goals

- <Goal 1>
- <Goal 2>
- <Goal 3>

## Technical Approach

- **<Category 1>:** <Details>
- **<Category 2>:** <Details>
- **<Category 3>:** <Details>

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
