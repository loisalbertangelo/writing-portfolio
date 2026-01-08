---
layout: default
title: Home
---

# Writing Portfolio

Public health, aging, and emergency preparedness writing with structured metadata.

## Featured Work

<div class="featured-articles">
  {% assign featured = site.articles | where: "status", "Published" | sort: "publish_date" | reverse | limit: 3 %}
  {% for article in featured %}
  <div class="article-card">
    <h3><a href="{{ article.url }}">{{ article.title }}</a></h3>
    <p><strong>{{ article.type }}</strong> | {{ article.role }} | {{ article.publish_date | date: "%Y" }}</p>
    <p>{{ article.excerpt }}</p>
  </div>
  {% endfor %}
</div>

## About This Portfolio

This site collects selected writing on aging, emergency preparedness, and health equity, organized with structured metadata for searchability and reuse.

- Browse all [articles](/articles/)
- Learn more [about this portfolio](/about/)
