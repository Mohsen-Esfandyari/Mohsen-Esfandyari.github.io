---
layout: single
title: "Publications"
permalink: /publications/
author_profile: true
classes: wide
---

{% include base_path %}

{%- comment -%}
Only show sections that have items.
Supported categories:
- Books:        books
- Journals:     journals, journal, journal-articles
- Conferences:  conferences, conference, workshop, workshops
{%- endcomment -%}

{%- comment -%} Build BOOKS {%- endcomment -%}
{% assign books = site.publications | where: "category", "books" | sort: "date" | reverse %}

{%- comment -%} Build JOURNALS (combine aliases) {%- endcomment -%}
{% assign journals = site.publications | where: "category", "journals" %}
{% assign j_more = site.publications | where: "category", "journal" %}
{% assign journals = journals | concat: j_more %}
{% assign j_more = site.publications | where: "category", "journal-articles" %}
{% assign journals = journals | concat: j_more %}
{% assign journals = journals | sort: "date" | reverse %}

{%- comment -%} Build CONFERENCES (combine aliases) {%- endcomment -%}
{% assign confs = site.publications | where: "category", "conferences" %}
{% assign c_more = site.publications | where: "category", "conference" %}
{% assign confs = confs | concat: c_more %}
{% assign c_more = site.publications | where: "category", "workshop" %}
{% assign confs = confs | concat: c_more %}
{% assign c_more = site.publications | where: "category", "workshops" %}
{% assign confs = confs | concat: c_more %}
{% assign confs = confs | sort: "date" | reverse %}

{%- if books.size > 0 -%}
## Books
{% for p in books %}
- **{{ p.title }}**  
  {{ p.authors }}. *{{ p.venue }}*, {{ p.date | date: "%Y" }}{% if p.note %}. {{ p.note }}{% endif %}.
  {% assign sep = "" %}
  {% if p.pdf or p.arxiv or p.doi or p.code or p.slides or p.poster %}
  <br>
  {% if p.pdf %}{{ sep }}[PDF]({{ p.pdf }}){% assign sep = " · " %}{% endif %}
  {% if p.arxiv %}{{ sep }}[arXiv]({{ p.arxiv }}){% assign sep = " · " %}{% endif %}
  {% if p.doi %}{{ sep }}[DOI]({{ p.doi }}){% assign sep = " · " %}{% endif %}
  {% if p.code %}{{ sep }}[Code]({{ p.code }}){% assign sep = " · " %}{% endif %}
  {% if p.slides %}{{ sep }}[Slides]({{ p.slides }}){% assign sep = " · " %}{% endif %}
  {% if p.poster %}{{ sep }}[Poster]({{ p.poster }}){% endif %}
  {% endif %}
{% endfor %}

{% endif %}

{%- if journals.size > 0 -%}
## Journal Articles
{% for p in journals %}
- **{{ p.title }}**  
  {{ p.authors }}. *{{ p.venue }}*, {{ p.date | date: "%Y" }}{% if p.note %}. {{ p.note }}{% endif %}.
  {% assign sep = "" %}
  {% if p.pdf or p.arxiv or p.doi or p.code or p.slides or p.poster %}
  <br>
  {% if p.pdf %}{{ sep }}[PDF]({{ p.pdf }}){% assign sep = " · " %}{% endif %}
  {% if p.arxiv %}{{ sep }}[arXiv]({{ p.arxiv }}){% assign sep = " · " %}{% endif %}
  {% if p.doi %}{{ sep }}[DOI]({{ p.doi }}){% assign sep = " · " %}{% endif %}
  {% if p.code %}{{ sep }}[Code]({{ p.code }}){% assign sep = " · " %}{% endif %}
  {% if p.slides %}{{ sep }}[Slides]({{ p.slides }}){% assign sep = " · " %}{% endif %}
  {% if p.poster %}{{ sep }}[Poster]({{ p.poster }}){% endif %}
  {% endif %}
{% endfor %}

{% endif %}

{%- if confs.size > 0 -%}
## Conference Papers
{% for p in confs %}
- **{{ p.title }}**  
  {{ p.authors }}. *{{ p.venue }}*, {{ p.date | date: "%Y" }}{% if p.note %}. {{ p.note }}{% endif %}.
  {% assign sep = "" %}
  {% if p.pdf or p.arxiv or p.doi or p.code or p.slides or p.poster %}
  <br>
  {% if p.pdf %}{{ sep }}[PDF]({{ p.pdf }}){% assign sep = " · " %}{% endif %}
  {% if p.arxiv %}{{ sep }}[arXiv]({{ p.arxiv }}){% assign sep = " · " %}{% endif %}
  {% if p.doi %}{{ sep }}[DOI]({{ p.doi }}){% assign sep = " · " %}{% endif %}
  {% if p.code %}{{ sep }}[Code]({{ p.code }}){% assign sep = " · " %}{% endif %}
  {% if p.slides %}{{ sep }}[Slides]({{ p.slides }}){% assign sep = " · " %}{% endif %}
  {% if p.poster %}{{ sep }}[Poster]({{ p.poster }}){% endif %}
  {% endif %}
{% endfor %}

{% endif %}
