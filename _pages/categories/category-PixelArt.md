---
title: "PixelArt"
layout: archive
permalink: categories/PixelArt
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.PixelArt %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}