---
layout: page
title: Statuslog
---
{% assign i_status = site.statuslog | sort:"date" | reverse %}

{% for status in i_status %}
  <p class="post-meta">{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y %H:%M" -%}
    <time class="dt-published" datetime="{{ status.date | date_to_xmlschema }}" itemprop="datePublished">
      {{ status.date | date: date_format }}
    </time>
    {%- if status.modified_date -%}
      ~ 
      {%- assign mdate = status.modified_date | date_to_xmlschema -%}
      <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
        {{ mdate | date: date_format }}
      </time>
    {%- endif -%}: </p>
> <strong>"{{ status.status }}</strong>"
<hr>
<br>
{% endfor %}