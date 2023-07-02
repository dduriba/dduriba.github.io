---
title: "Jekyll"
layout: archive
permalink: categories/jekyll
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
---

{% assign posts = site.categories.jekyll %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}