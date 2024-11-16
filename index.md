---
layout: home
---
<link rel="shortcut icon" type="image/x-icon" href="/favicon.ico">

## Inicio

**En que ando ahora:** [Ahora](/now.html)

## Ultimos posts

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
    {%- endif -%} - <a href=".{{ post.url }}">{{ post.title }}</a></p> 
{% endfor %}

<a href="/blog.html">Todos los posts</a>

<lightning-widget 
  name="Zetta Founder" 
  accent="#000000" 
  to="zettafounder@stacker.news" 
  image="https://nostrcheck.me/media/e140a3ea5b9434a8e853c9264bdc10a5b85c765114b37cbf4850f520c0e40975/783d7f557b8e84d48dcf14e83fecb99c8ff64cc4cd671c55b2fa03264e18ea7f.webp" 
/>
<script src="https://embed.twentyuno.net/js/app.js"></script>

<a rel="me" href="https://mstdn.mx/@jpz"></a>