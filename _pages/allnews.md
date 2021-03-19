---
title: "News"
layout: textlay
excerpt: "Physics of social systems group at the Max Planck Institute for Dynamics and Self-Organization"
sitemap: false
permalink: /allnews.html
---

# News

{% for article in site.data.news %}
<p>{{ article.date }} <br>
<em>{{ article.headline }}</em></p>
{% endfor %}
