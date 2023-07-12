---
title: "Data Structure"
layout: archive
permalink: categories/Data_Structure
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.Data_Structure %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}