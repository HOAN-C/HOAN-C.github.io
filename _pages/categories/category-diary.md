---
title: "Diary"
layout: single
permalink: /diary/
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.diary %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
