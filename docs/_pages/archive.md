---
permalink: /archive
layout: page
title: Archive
---

<div class="post">

  {% assign sorted_posts = site.posts | sort: 'date' | reverse %}
  {% assign current_month = "" %}

  <ul style="list-style-type: none;"> <!-- Remove bullets for the months -->
    {% for post in sorted_posts %}
      {% assign post_month = post.date | date: "%B %Y" %}
      
      <!-- Check if we're in a new month -->
      {% if post_month != current_month %}
        {% if current_month != "" %}
          </ul> <!-- Close the previous month's list properly without being printed -->
        {% endif %}
        
        <!-- Set current month and create a new expandable section -->
        {% assign current_month = post_month %}
        <li>
          <h3 class="month-header" style="cursor: pointer;" onclick="toggleMonth('{{ current_month }}')">
            &#x25B6; {{ current_month }} <!-- Arrow that rotates when expanded -->
          </h3>
          <ul id="month-{{ current_month }}" style="display: none; list-style-type: none;"> <!-- Collapsible posts list, no bullets -->
      {% endif %}
      
      <!-- Display the post for the current month -->
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a> ({{ post.date | date: "%Y-%m-%d" }})
      </li>
      
    {% endfor %}
    
    {% if current_month != "" %}
      </ul> <!-- Close the last month's list properly -->
    {% endif %}
  </ul> <!-- Close the outer <ul> properly -->
</div>

<!-- Add some JavaScript to handle the collapsing/expanding functionality -->
<script>
  function toggleMonth(month) {
    var list = document.getElementById('month-' + month);
    var header = document.querySelector('h3.month-header[onclick="toggleMonth(\'' + month + '\')"]');
    
    if (list.style.display === "none") {
      list.style.display = "block";
      header.innerHTML = "&#x25BC; " + month; // Change to downward arrow
    } else {
      list.style.display = "none";
      header.innerHTML = "&#x25B6; " + month; // Change to right arrow
    }
  }
</script>

<!-- Include the tag archive -->
{% include archive.html %}
