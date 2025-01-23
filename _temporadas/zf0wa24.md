---
layout: temporada
author: Zetta Founder
title: "Temporada ZF 0"
tags: temporadas
date: 2024-10-01 05:00:00 -0600
fin: 2024-12-31 05:00:00 -0600
update: 2024-11-27 20:11:00 -0600
---

Esta es la temporada 0 como Zetta Founder, es una temporada de prueba para observarme como funciono si hago las cosas diferente. Si todo sale bien como hasta ahora, en el 2025 iniciamos la temporada 1.

Por lo mientras estoy en la fase beta, tanto de un "nuevo yo" como de ciertos proyectos. Estos proyectos no los puedo compartir por diversas razones. Una de ellas es que quiero que estos proyectos no estén ligados a mi identidad digital por motivos de privacidad y seguridad.

## Lanzamientos

- Podcast: <a target="_blank" href="https://saqh.lepodca.st">Saqh</a> Temporada 0
- Nuevo blog personal en github: [Zetta Founder](https://zettafounder.github.io/)
- Nuevo blog de tecnología: <a target="_blank" href="https://zettafounder.github.io/zettabitz/">Zetta Bitz</a>

## Posts de esta temporada

<ul>{% for post in site.tags["zf0"] %}
  <li>{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <time class="dt-published" datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">
      {{ post.date | date: date_format }}
    </time>
    {%- if post.modified_date -%}
      ~ 
      {%- assign mdate = post.modified_date | date_to_xmlschema -%}
      <time class="dt-modified" datetime="{{ mdate }}" itemprop="dateModified">
        {{ mdate | date: date_format }}
      </time>
    {%- endif -%} - <a href=".{{ post.url }}">{{ post.title }}</a></li> 
{% endfor %}</ul>

## Fin de temporada

Hoy (27.11.2024) doy por concluida la temporada ZF.0.WA.24, fue interesante, aprendi mucho y creci mucho tambien. Nos vemos la proxima temporada en 2025, con una nueva temporada del podcast y con nuevas entradas en el blog. Tambien habran un par de cambios interesantes.

Hasta el proximo año, feliz navidad y año nuevo a todos.