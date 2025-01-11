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
> <strong>"{{ status.status }}"</strong>
{% endfor %}

-----
<br>

## Contacto

Telegram: <a href="https://t.me/zettafounder" target="_blank">zettafounder</a>
Signal: <a href="https://t.me/zettafounder" target="_blank">zettafounder.21</a>
Keybase: <a href="https://keybase.io/zettafounder" target="_blank">zettafounder</a>
SimpleX: <a href="https://simplex.chat/contact#/?v=2-7&smp=smp%3A%2F%2F6iIcWT_dF2zN_w5xzZEY7HI2Prbh3ldP07YTyDexPjE%3D%40smp10.simplex.im%2FU3BAGZl1VzC3nIIpMH-DrveSKaUx00PV%23%2F%3Fv%3D1-3%26dh%3DMCowBQYDK2VuAyEAKXdWImoDNMmiLVBMzcfhSfI8m429pqcaqFNOmPeXUmc%253D%26srv%3Drb2pbttocvnbrngnwziclp2f4ckjq65kebafws6g4hy22cdaiv5dwjqd.onion" target="_blank">Zetta Founder</a>
Email: <a href="mailto:zettafounder@proton.me" target="_blank">zettafounder@proton.me</a>

-----
<br>

PGP: <a href="https://keys.openpgp.org/vks/v1/by-fingerprint/059C841B4250D91B0B6B1A41D255C49C8C375104" target="_blank">D255 C49C 8C37 5104</a>

-----
<br>

Todos mis enlaces: <a href="https://bio.link/zettafounder" target="_blank">Bio Link</a>, <a href="https://nostree.me/npub1u9q286jmjs6236zneynyhhqs5ku9caj3zjehe06g2r6jps8yp96sml8cyj" target="_blank">Nostree</a>.

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

---
<br>