---
title: "Data Structure"
layout: archive
permalink: categories/dataStructure
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.dataStructure %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}