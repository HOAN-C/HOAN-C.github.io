---
title: "Tech"
layout: single
permalink: /tech/
author_profile: true
sidebar:
  nav: "docs"
---

{% assign posts = site.categories.tech %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
