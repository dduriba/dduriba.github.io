---
title: "OS"
layout: archive
permalink: categories/os
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.os %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}