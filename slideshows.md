---
layout: page
title: 幻灯片
---

{% assign decks = site.pages | where: "layout", "slideshow" %}
{% if decks.size > 0 %}
<ul class="deck-list">
  {% for p in decks %}
  <li><a href="{{ p.url | relative_url }}">{{ p.title }}</a></li>
  {% endfor %}
</ul>
{% else %}
<p>还没有幻灯片。参考 <a href="{{ '/slideshow-demo/' | relative_url }}">示例</a>，用 <code>layout: slideshow</code> 新建一个页面即可。</p>
{% endif %}
