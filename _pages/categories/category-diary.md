---
title: "Diary"
layout: single
permalink: /diary/
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.diary %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
