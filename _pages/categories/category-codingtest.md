---
title: "Coding test"
layout: single
permalink: /codingtest/
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.codingtest %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
