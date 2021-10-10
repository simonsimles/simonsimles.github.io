---
layout: default
title: Short Posts/Tweets
---
<h1 class="page-heading">{{ page.title }}</h1>

{% assign posts = site.shorts | reverse %}
{% for post in posts %}
<div class="shorts-article">
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
</div>
{% endfor %}
