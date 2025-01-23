---
layout: temporada
author: Zetta Founder
title: "Temporada JPZ 0"
tags: temporadas
date: 2023-10-01 10:25:00 -0600
fin: 2024-06-20 11:35:00 -0600
update: 2024-11-16 04:39:00 -0600
---

Esta temporada inicio antes de siquiera imaginar escribir un blog, a media temporada comencé a escribir en un canal privado en <a href="https://t.me/+W7s4TQcPd1NlZDlh" target="_blank">Telegram</a> y paralelamente en mi blog en <a href="https://buymeacoffee.com/zettafounder/posts" target="_blank">Buy Me A Coffee</a>.

## Lanzamientos

- Inicie InMyMind (publicaciones privadas)
    - Temporada 1 de InMyMind en YouTube
    - Posts diarios en el <a href="https://t.me/+W7s4TQcPd1NlZDlh" target="_blank">canal de Telegram</a>
    - Posts constantes en mi blog de <a href="https://buymeacoffee.com/zettafounder/posts" target="_blank">Buy Me A Coffee</a>

> Actualmente, tanto el canal de Telegram y el blog en Buy Me A Coffee son de acceso privado.

**Estoy trabajando para hacer parte del contenido público.**

## Posts de la temporada

<ul>{% for post in site.tags["jpz0"] %}
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