---
title: Posts
layout: default
---

{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
{% for post in site.posts %}
<span class="post-meta">{{ post.date | date: date_format }}</span>
<h3>
  <a class="post-link" href="{{ post.url | relative_url }}">
    {{ post.title | escape }}
  </a>
</h3>
<div class="posts-content">
{{ post.content }}
<div align="right">
<small>
<a href="{{ post.url }}">
  {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y - %H:%M" -%}
  <time class="dt-published" datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">
    {{ post.date | date: date_format }}
  </time>
  - Go to post</a>
  </small>
  </div>
</div>
{% endfor %}
