---
title: "Algorithm"
layout: archive
permalink: /categories/algorithm/
author_profile: true
types: posts
---

{% assign posts = site.categories['Algorithm']%}
{% for post in posts %}
{% include archive-single.html type=page.entries_layout %}
{% endfor %}
