---
layout: page
title: Temporadas
---

<ul>
  {% for temporada in site.temporadas %}
    <li>
      <h4>{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <time class="dt-published" datetime="{{ temporada.date | date_to_xmlschema }}" itemprop="datePublished">
        {{ temporada.date | date: date_format }}
        </time>
        {%- if temporada.modified_date -%}
        ~ 
        {%- assign mdate = temporada.modified_date | date_to_xmlschema -%}
        <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
            {{ mdate | date: date_format }}
        </time>
        {%- endif -%} - <a href="{{ temporada.url }}">{{ temporada.title }}</a></h4>
    </li>
  {% endfor %}
</ul>