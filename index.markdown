---
layout: default
---

<h1>Welcome</h1>

<h2>Latest short post/tweet</h2>
{% assign post = site.shorts | last %}
<div class="shorts-content">
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

<h2>Latest post</h2>
{% assign post = site.posts | first %}
{% if post %}
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
{% endif %}
