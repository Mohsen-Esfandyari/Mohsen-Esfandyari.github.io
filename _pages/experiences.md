---
title: Work Experiences
permalink: /wexperiences/
layout: single
author_profile: true
classes: wide
---

{% assign items = site.experiences | sort: "date_start" | reverse %}

{% for item in items %}
### {{ item.role }} — {{ item.company }}
**{{ item.location }}** · *{% if item.date_start %}{{ item.date_start | date: "%b %Y" }}{% endif %} – {% if item.date_end and item.date_end != "present" %}{{ item.date_end | date: "%b %Y" }}{% else %}Present{% endif %}*


{{ item.content }}

---

{% endfor %}
