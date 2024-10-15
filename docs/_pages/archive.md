---
permalink: /archive
layout: default
title: Archive
---

<div class="post">
  <ul>
  {% for post in site.posts %}
    <li>
      <a href=".{{ post.url }}">{{ post.title }}</a> ({{ post.date | date: "%Y-%m-%d" }})
    </li>
  {% endfor %}
</ul>
</div>

<!-- Include archive with extra spacing before and after the dividing line -->
<hr style="margin-top: 30px; margin-bottom: 30px;"> <!-- Adjust these values as needed -->
{% include archive.html %}

