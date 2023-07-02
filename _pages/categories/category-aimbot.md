---
title: "PROJECT AimBot"
layout: archive
permalink: categories/aimbot
author_profile: true
sidebar_main: true
sidebar:
    nav: "docs"
---

{% assign posts = site.categories.aimbot %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}