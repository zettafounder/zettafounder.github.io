---
layout: page
title: Temporadas
---
{% assign i_temporadas = site.temporadas | sort:"date" | reverse %}

{% for temporada in i_temporadas %}
  <h3><a href="{{ temporada.url }}">{{ temporada.title }}</a></h3><p class="post-meta"> {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <time class="dt-published" datetime="{{ temporada.date | date_to_xmlschema }}" itemprop="datePublished">
        {{ temporada.date | date: date_format }}
        </time>
        {%- if temporada.modified_date -%}
        ~ 
        {%- assign mdate = temporada.modified_date | date_to_xmlschema -%}
        <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
            {{ mdate | date: date_format }}
        </time>
        {%- endif -%} - {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
        <time class="dt-published" datetime="{{ temporada.fin | date_to_xmlschema }}" itemprop="datePublished">
        {{ temporada.fin | date: date_format }}
        </time>
        {%- if temporada.modified_date -%}
        ~ 
        {%- assign mdate = temporada.modified_date | date_to_xmlschema -%}
        <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
            {{ mdate | date: date_format }}
        </time>
        {%- endif -%}
  </p>
{% endfor %}