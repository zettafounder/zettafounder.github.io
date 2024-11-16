---
layout: page
title: Blog
---
<link rel="shortcut icon" type="image/x-icon" href="/favicon.ico">

{% for post in site.posts %}
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

<a rel="me" href="https://mstdn.mx/@jpz"></a>
<a rel="me" href="https://zettafounder.github.io/feed.xml">RSS</a>

<script data-name="BMC-Widget" data-cfasync="false" src="https://cdnjs.buymeacoffee.com/1.0.0/widget.prod.min.js" data-id="zettafounder" data-description="Support me on Buy me a coffee!" data-message="" data-color="#5F7FFF" data-position="Right" data-x_margin="18" data-y_margin="18"></script>