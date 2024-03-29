---
title: "C#"
layout: archive
permalink: categories/C#
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
classes: wide
---

{% assign posts = site.categories.C# %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}