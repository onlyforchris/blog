---
layout: page
title: 幻灯片
---
<style>
  .deck-cta { display:flex; align-items:center; justify-content:space-between; gap:1rem; flex-wrap:wrap; padding:1.2rem 1.4rem; border-radius:14px; background:var(--accent-soft); border:1px solid var(--accent); margin-bottom:2rem; }
  .deck-cta .t { font-weight:700; }
  .deck-cta .s { color:var(--muted); font-size:.9rem; margin-top:.2rem; }
  .deck-cta .btns { display:flex; gap:.7rem; flex-wrap:wrap; }
  .ctl-btn { padding:.6rem 1.1rem; border-radius:99px; border:1px solid var(--accent); background:var(--surface); color:var(--ink); font-size:.9rem; cursor:pointer; text-decoration:none; transition:.15s; }
  .ctl-btn:hover { transform:translateY(-1px); background:var(--accent); color:#fff; }
  .ctl-btn.solid { background:var(--accent); color:#fff; border-color:var(--accent); }
  .ctl-btn.solid:hover { background:#4335cf; }
  .deck-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(240px,1fr)); gap:1rem; }
  .deck-card { display:block; padding:1.4rem 1.5rem; border-radius:16px; background:var(--surface); border:1px solid var(--line); text-decoration:none; color:var(--ink); transition:transform .18s ease, border-color .18s ease, box-shadow .18s ease; }
  .deck-card:hover { transform:translateY(-3px); border-color:var(--accent); box-shadow:0 16px 36px -24px rgba(79,70,229,.5); }
  .deck-card-title { font-weight:700; font-size:1.15rem; letter-spacing:-.01em; margin-bottom:.4rem; }
  .deck-card-desc { color:var(--muted); font-size:.9rem; line-height:1.5; margin-bottom:.9rem; }
  .deck-card .start { color:var(--accent); font-size:.85rem; font-weight:600; }
  .deck-empty { color:var(--muted); }
</style>

<div class="deck-cta">
  <div>
    <div class="t">想放一套自己的演示？</div>
    <div class="s">一个 <code>layout: slideshow</code> 页面 + 一段段 <code>&lt;section class="slide"&gt;</code>，就能放映。</div>
  </div>
  <div class="btns">
    <button class="ctl-btn solid" id="copyTpl">复制起点模板</button>
    <a class="ctl-btn" href="{{ '/write-html-slides/' | relative_url }}">查看教程</a>
    <a class="ctl-btn" href="{{ '/apple-demo.html' | relative_url }}" target="_blank">Apple 风格演示 ↗</a>
  </div>
</div>

{% assign decks = site.pages | where: "layout", "slideshow" %}
{% if decks.size == 0 %}
<p class="deck-empty">还没有幻灯片。点上方"复制起点模板"，或照<a href="{{ '/blog/write-html-slides/' | relative_url }}">教程</a>新建一个即可。</p>
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

<script>
(function () {
  var btn = document.getElementById('copyTpl');
  if (!btn) return;
  var tpl = '---\nlayout: slideshow\ntitle: 我的演示\ndescription: 一句话介绍这套演示\n---\n<section class="slide"><div><h1>第一页</h1><p>副标题或一句话。</p></div></section>\n<section class="slide"><div><h2>要点</h2><ul><li>第一点</li><li>第二点</li></ul></div></section>\n<section class="slide"><div><h2>结束</h2><p class="accent">谢谢。</p></div></section>';
  var done = function () { var o = btn.textContent; btn.textContent = '已复制'; btn.classList.remove('solid'); setTimeout(function () { btn.textContent = o; btn.classList.add('solid'); }, 1500); };
  btn.addEventListener('click', function () {
    if (navigator.clipboard && navigator.clipboard.writeText) { navigator.clipboard.writeText(tpl).then(done).catch(function () { fb(); }); } else { fb(); }
    function fb() { var ta = document.createElement('textarea'); ta.value = tpl; document.body.appendChild(ta); ta.select(); try { document.execCommand('copy'); } catch (e) {} document.body.removeChild(ta); done(); }
  });
})();
</script>
