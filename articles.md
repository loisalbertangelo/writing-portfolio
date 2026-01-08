---
layout: default
title: Articles
permalink: /articles/
---

# Articles

A collection of writing on aging, emergency preparedness, and health equity.

<table>
  <thead>
    <tr>
      <th>Year</th>
      <th>Title</th>
      <th>Type</th>
      <th>Role</th>
      <th>Topics</th>
    </tr>
  </thead>
  <tbody>
  {% assign sorted = site.articles | sort: "publish_date" | reverse %}
  {% for article in sorted %}
    <tr>
      <td>{{ article.publish_date | date: "%Y" }}</td>
      <td><a href="{{ article.url }}">{{ article.title }}</a></td>
      <td>{{ article.type }}</td>
      <td>{{ article.role }}</td>
      <td>
        {% for t in article.topics %}
          {{ t }}{% unless forloop.last %}, {% endunless %}
        {% endfor %}
      </td>
    </tr>
  {% endfor %}
  </tbody>
</table>

## Browse by Topic

{% assign all_topics = site.articles | map: "topics" | join: "," | split: "," | uniq | sort %}
{% for topic in all_topics %}
- {{ topic }}
{% endfor %}
