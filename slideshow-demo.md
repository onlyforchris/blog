---
layout: slideshow
title: 幻灯片演示
---

<section class="slide">
  <div>
    <h1>博客也能放<span class="accent">幻灯片</span></h1>
    <p>像你现在这样，全屏放映、键盘翻页。</p>
    <p>按 <code>→</code> <code>空格</code> 下一页 · <code>←</code> 上一页 · <code>F</code> 全屏</p>
  </div>
</section>

<section class="slide">
  <div>
    <h2>怎么新建一个幻灯片</h2>
    <p>在博客里放一个页面，用 <code>layout: slideshow</code>，内容是一段段 <code>&lt;section class="slide"&gt;</code>。</p>
    <p>一段就是一个页面。</p>
  </div>
</section>

<section class="slide">
  <div>
    <h2>示例结构</h2>
    <pre><code>---
layout: slideshow
title: 我的演示
---
&lt;section class="slide"&gt;
  &lt;h1&gt;第一页&lt;/h1&gt;
&lt;/section&gt;
&lt;section class="slide"&gt;
  &lt;h2&gt;第二页&lt;/h2&gt;
&lt;/section&gt;</code></pre>
  </div>
</section>

<section class="slide">
  <div>
    <h2>已经内置的交互</h2>
    <ul>
      <li><code>→</code>/<code>空格</code>/<code>回车</code> 下一页</li>
      <li><code>←</code>/<code>PageUp</code> 上一页</li>
      <li><code>F</code> 全屏 · <code>T</code> 明暗切换 · <code>Home</code>/<code>End</code> 跳头尾</li>
      <li>右上角 <code>☰</code> / <code>M</code> 打开目录，点任意标题直接跳到那一页</li>
      <li>右下角 ↦ / 点击右半边翻页，底部进度条 + 页码</li>
    </ul>
  </div>
</section>

<section class="slide">
  <div>
    <h2>这就够了</h2>
    <p>把 <code>layout: slideshow</code> 塞进一个页面，填上你的 HTML 内容，就是一个可放映的演示。</p>
    <p class="accent">开始动手放你的 PPT 吧。</p>
  </div>
</section>
