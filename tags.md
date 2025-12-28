---
layout: default
title: Posts by Tag
permalink: /tags/
nav_show: true
---

<!-- JavaScript to filter posts based on the URL hash -->
<script>
  function filterByHash() {
    const hash = window.location.hash.substring(1); // Get tag from #diy
    const sections = document.querySelectorAll('.tag-section');
    
    if (hash) {
      sections.forEach(section => {
        section.style.display = (section.id === hash) ? 'block' : 'none';
      });
    } else {
      // Show everything if there is no hash
      sections.forEach(section => section.style.display = 'block');
    }
  }

  window.addEventListener('hashchange', filterByHash);
  window.addEventListener('DOMContentLoaded', filterByHash);
</script>

{% assign sorted_tags = site.tags | sort %}
{% for tag_pair in sorted_tags %}
  {% assign tag_name = tag_pair[0] %}
  {% assign tag_posts = tag_pair[1] %}
  {% assign tag_id = tag_name | slugify %}

  <div id="{{ tag_id }}" class="tag-section" style="display:none;">
    <h2>Posts tagged with: #{{ tag_name }}</h2>
    <ul>
      {% for post in tag_posts %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <small>— {{ post.date | date: "%b %d, %Y" }}</small>
        </li>
      {% endfor %}
    </ul>
    <hr>
  </div>
{% endfor %}

<p><a href="{{ '/tags/' | relative_url }}">View all tags</a></p>
