---
title: Academic Experiences
permalink: /aexperiences/
layout: single
author_profile: true
classes: wide
---

## Research Assistantships
{% assign ras = site.academic | where: "category", "RA" | sort: "date" | reverse %}
{% for item in ras %}
### {{ item.title }}
*{{ item.venue }}* · {{ item.term }} — **Research Assistant**{% if item.supervisor %} (Supervisor: {{ item.supervisor }}){% endif %}

{% if item.excerpt %}{{ item.excerpt }}{% endif %}

---
{% endfor %}

## Teaching Assistantships
{% assign tas = site.academic | where: "category", "TA" | sort: "date" | reverse %}
{% for item in tas %}
### {{ item.title }}
*{{ item.venue }}* · {{ item.term }} — **Teaching Assistant**{% if item.instructor %} (Instructor: {{ item.instructor }}){% endif %}

{% if item.excerpt %}{{ item.excerpt }}{% endif %}

---
{% endfor %}

