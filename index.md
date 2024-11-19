---
layout: home
update: 2024-11-19 01:44:00 -0600
---
<link rel="shortcut icon" type="image/x-icon" href="/favicon.ico">

> **En que ando [ahora](/now.html)**

## Ultimo estado

{% assign i_status = site.statuslog | sort:"date" | reverse %}

{% for status in i_status | limit: 1 %}
  <p class="post-meta">{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <time class="dt-published" datetime="{{ status.date | date_to_xmlschema }}" itemprop="datePublished">
      {{ status.date | date: date_format }}
    </time>
    {%- if status.modified_date -%}
      ~ 
      {%- assign mdate = status.modified_date | date_to_xmlschema -%}
      <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
        {{ mdate | date: date_format }}
      </time>
    {%- endif -%}</p><p>Status: "{{ status.status }}"</p><hr>
{% endfor %}

## Ultimos posts

{% assign i_posts = site.posts %}

{% for post in i_posts | limit: 10 %}
  <p>{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <time class="dt-published" datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">
      {{ post.date | date: date_format }}
    </time>
    {%- if post.modified_date -%}
      ~ 
      {%- assign mdate = post.modified_date | date_to_xmlschema -%}
      <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
        {{ mdate | date: date_format }}
      </time>
    {%- endif -%} - <a href=".{{ post.url }}">{{ post.title }}</a></p> 
{% endfor %}

<a href="/blog.html">Todos los posts</a> • <a target="_blank" href="https://zettafounder.github.io/feed.xml">RSS</a>

<a rel="me" href="https://mstdn.mx/@jpz"></a>