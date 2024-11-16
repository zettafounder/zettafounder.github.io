---
layout: page
title: Temporadas
---
{% assign i_temporadas = site.temporadas | sort:"date" %}

<ul>
  {% for temporada in i_temporadas %}
    <li>
      <h4><a href="{{ temporada.url }}">{{ temporada.title }}</a> - {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
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
        {%- endif -%}</h4>
    </li>
  {% endfor %}
</ul>