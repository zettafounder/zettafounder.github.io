---
layout: home
---
<link rel="shortcut icon" type="image/x-icon" href="/favicon.ico">
<a rel="me" href="https://mstdn.mx/@jpz"></a>

**En que ando ahora:** [Ahora](/now.html)

**Temporada actual:**  [ZF.0.WA.24](https://zettafounder.github.io/temporadas/zf0wa24.html)

## Ultimos posts

{% assign i_posts = site.posts %}

{% for post in i_posts | limit: 3 %}
  <h4>{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <time class="dt-published" datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">
      {{ post.date | date: date_format }}
    </time>
    {%- if post.modified_date -%}
      ~ 
      {%- assign mdate = post.modified_date | date_to_xmlschema -%}
      <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
        {{ mdate | date: date_format }}
      </time>
    {%- endif -%} - <a href=".{{ post.url }}">{{ post.title }}</a></h4> 
{% endfor %}