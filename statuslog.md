---
layout: page
title: Statuslog
---

> Actualización de estado

{% assign i_status = site.statuslog | sort:"date" | reverse %}

{% for status in i_status %}
  <h4>{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <time class="dt-published" datetime="{{ status.date | date_to_xmlschema }}" itemprop="datePublished">
      {{ status.date | date: date_format }}
    </time>
    {%- if status.modified_date -%}
      ~ 
      {%- assign mdate = status.modified_date | date_to_xmlschema -%}
      <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
        {{ mdate | date: date_format }}
      </time>
    {%- endif -%} - <a href=".{{ status.url }}">{{ status.content }}</a></h4> 
{% endfor %}

<a rel="me" href="https://zettafounder.github.io/feed.xml">RSS</a>