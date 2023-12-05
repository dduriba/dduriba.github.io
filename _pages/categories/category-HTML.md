---
title: "HTML"
layout: archive
permalink: categories/HTML
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.HTML %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}