---
permalink: /archive
layout: page
title: Archive
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href=".{{ post.url }}">{{ post.title }}</a> ({{ post.date | date: "%Y-%m-%d" }})
    </li>
  {% endfor %}
</ul>

<!-- Include archive with extra spacing before and after the dividing line -->
<hr style="margin-top: 30px; margin-bottom: 30px;"> <!-- Adjust these values as needed -->
{% include archive.html %}
