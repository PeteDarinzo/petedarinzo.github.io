---
layout: page
menu: projects
title: Projects
permalink: /projects/
---


<ul class="post-list">
  {%- for post in site.categories['development'] -%}
  <li>
  {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%} 
  <span class="post-meta">
  {{ post.data | data: date_formatF }}
  </span>
  <h3>
    <a class="post-link" href="{{ post.url | relative_url }}">
      {{ post.title | escape }}
    </a>
  </h3>
  {%- if site.show_excerpts -%}
  {{ post.excerpt }}
  {%- endif -%}
  </li>
  {%- endfor -%}
<ul>