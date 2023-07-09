---
title: "C/C++/C#"
layout: archive
permalink: categories/c
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.c %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}