---
title: "Back-end"
layout: archive
permalink: /categories/back-end/
author_profile: true
types: posts
---

{% assign posts = site.categories['Back-end']%}
{% for post in posts %}
{% include archive-single.html type=page.entries_layout %}
{% endfor %}
