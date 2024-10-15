---
permalink: /archive
layout: page
title: Archive
---

<div class="post">
  <!-- Include the archive list -->
  {% include archive_list.html %}
</div>

<!-- Add your script for toggling the month -->
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

{% include archive.html %}
