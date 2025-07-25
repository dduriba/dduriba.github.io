---
title: "Aseprite"
layout: archive
permalink: categories/Aseprite
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.Aseprite %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}