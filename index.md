---
layout: home
update: 2024-11-19 01:44:00 -0600
---
{% assign i_status = site.statuslog | sort:"date" | reverse %}
{% for status in i_status | limit: 1 %}
  <p class="post-meta">{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    Último estado, <time class="dt-published" datetime="{{ status.date | date_to_xmlschema }}" itemprop="datePublished">
      {{ status.date | date: date_format }}
    </time>
    {%- if status.modified_date -%}
      ~ 
      {%- assign mdate = status.modified_date | date_to_xmlschema -%}
      <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
        {{ mdate | date: date_format }}
      </time>
    {%- endif -%}:
    {%- if status.author -%}
        • {% for author in status.author %}
          <span itemprop="author" itemscope itemtype="http://schema.org/Person">
            <span class="p-author h-card" itemprop="name">{{ author }}:</span></span>
            {%- if forloop.last == false %}, {% endif -%}
        {% endfor %}
      {%- endif -%}</p>
> "{{ status.status }}"
{% endfor %}

-----

<br>

## Últimos posts del blog

{% assign i_posts = site.posts %}

{% for post in i_posts | limit: 3 %}
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
    {%- endif -%} - <a href=".{{ post.url }}"><strong>{{ post.title }}</strong></a></p> 
{% endfor %}

[Todos los posts](/blog.html) • <a target="_blank" href="https://zettafounder.github.io/feed.xml">RSS</a>