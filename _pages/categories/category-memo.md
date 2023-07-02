---
title: "Memo"
layout: archive
permalink: categories/memo
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
---

{% assign posts = site.categories.memo %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}