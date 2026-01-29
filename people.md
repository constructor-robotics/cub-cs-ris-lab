---
title: People
layout: default
nav_order: 4
has_toc: false
has_children: true
---

# People
{: .no_toc }

This page lists all lab members and links to their WIP entries.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

Lab members are listed by role, with links to their research contributions.

{% assign people = site.pages | where_exp: "page", "page.path contains 'people/'" | where_exp: "page", "page.name != 'TEMPLATE.md'" | where_exp: "page", "page.group" %}

## Faculty/Staff

{% assign faculty = people | where: "group", "faculty" | where: "status", "active" | sort: "last_name" %}
{% if faculty.size > 0 %}
{% for person in faculty %}
### {% if person.public_url %}[{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}]({{ person.public_url }}){% else %}{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}{% endif %}

{% if person.research_focus %}**Research Focus:** {{ person.research_focus }}{% endif %}
**Status:** {{ person.status }}

{% endfor %}
{% else %}
*No faculty members yet.*
{% endif %}

## PhD Students

{% assign phd = people | where: "group", "phd" | where: "status", "active" | sort: "last_name" %}
{% if phd.size > 0 %}
{% for person in phd %}
### {% if person.public_url %}[{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}]({{ person.public_url }}){% else %}{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}{% endif %}

{% if person.research_focus %}**Research Focus:** {{ person.research_focus }}{% endif %}
**Status:** {{ person.status }}

{% endfor %}
{% else %}
*No PhD students yet.*
{% endif %}

## Master Students

{% assign masters = people | where: "group", "masters" | where: "status", "active" | sort: "last_name" %}
{% if masters.size > 0 %}
{% for person in masters %}
### {% if person.public_url %}[{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}]({{ person.public_url }}){% else %}{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}{% endif %}

{% if person.research_focus %}**Research Focus:** {{ person.research_focus }}{% endif %}
**Status:** {{ person.status }}

{% endfor %}
{% else %}
*No master students yet.*
{% endif %}

## Undergraduate Students

{% assign undergrad = people | where: "group", "undergrad" | where: "status", "active" | sort: "last_name" %}
{% if undergrad.size > 0 %}
{% for person in undergrad %}
### {% if person.public_url %}[{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}]({{ person.public_url }}){% else %}{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}{% endif %}

{% if person.research_focus %}**Research Focus:** {{ person.research_focus }}{% endif %}
**Status:** {{ person.status }}

{% endfor %}
{% else %}
*No undergraduate students yet.*
{% endif %}

## External Collaborators

{% assign external = people | where: "group", "external" | where: "status", "active" | sort: "last_name" %}
{% if external.size > 0 %}
{% for person in external %}
### {% if person.public_url %}[{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}]({{ person.public_url }}){% else %}{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}{% endif %}

{% if person.research_focus %}**Research Focus:** {{ person.research_focus }}{% endif %}
**Status:** {{ person.status }}

{% endfor %}
{% else %}
*No external collaborators yet.*
{% endif %}

---

## Alumni

{% assign alumni = people | where: "status", "inactive" | sort: "last_name" %}
{% if alumni.size > 0 %}
{% for person in alumni %}
- {% if person.public_url %}[{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}]({{ person.public_url }}){% else %}{{ person.honorific_title }} {{ person.first_name }} {{ person.last_name }}{% endif %} ({{ person.group | capitalize }}) - {% if person.offboard == "yes" %}Offboarded{% else %}NOT Offboarded{% endif %}
{% endfor %}
{% else %}
*No alumni yet.*
{% endif %}
