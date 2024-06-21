---
title: "알고리즘"
layout: archive
permalink: categories/algoritm
author_profile: true
types: posts
---

{% assign posts = site.categories['algoritm']%}
{% for post in posts %}
{% include archive-single.html type=page.entries_layout %}
{% endfor %}
