---
title: "Algorithm"
layout: single
permalink: /algorithm/
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.algorithm %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
