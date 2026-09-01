---
layout: page
title: 幻灯片
---
<style>
  .deck-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(240px,1fr)); gap:1rem; }
  .deck-card { display:block; padding:1.4rem 1.5rem; border-radius:16px; background:var(--surface); border:1px solid var(--line); text-decoration:none; color:var(--ink); transition:transform .18s ease, border-color .18s ease, box-shadow .18s ease; }
  .deck-card:hover { transform:translateY(-3px); border-color:var(--accent); box-shadow:0 16px 36px -24px rgba(79,70,229,.5); }
  .deck-card-title { font-weight:700; font-size:1.15rem; letter-spacing:-.01em; margin-bottom:.4rem; }
  .deck-card-desc { color:var(--muted); font-size:.9rem; line-height:1.5; margin-bottom:.9rem; }
  .deck-card .start { color:var(--accent); font-size:.85rem; font-weight:600; }
  .deck-empty { color:var(--muted); }
</style>

{% assign decks = site.pages | where: "layout", "slideshow" %}
{% if decks.size == 0 %}
<p class="deck-empty">还没有幻灯片。用小例子 <a href="{{ '/slideshow-demo/' | relative_url }}">示例</a>，用一个 <code>layout: slideshow</code> 的页面写 <code>&lt;section class="slide"&gt;</code> 即可。</p>
{% else %}
<div class="deck-grid">
  {% for p in decks %}
  <a class="deck-card" href="{{ p.url | relative_url }}">
    <div class="deck-card-title">{{ p.title }}</div>
    {% if p.description %}<div class="deck-card-desc">{{ p.description }}</div>{% endif %}
    <span class="start">开始放映 →</span>
  </a>
  {% endfor %}
</div>
{% endif %}
