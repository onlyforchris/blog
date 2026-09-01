---
layout: post
title: 用 HTML 写一套能放映的幻灯片：从这里开始
date: 2026-09-01
tags: [幻灯片, 演示, HTML, 教程]
section: 工程判断
---

这个博客内置了一个**放映功能**：你只要写一段 HTML，就能在博客里全屏放映、目录跳页、自动播放。这篇是写给自己的备忘，也算教你三分钟上手。

## 一句话：一个页面 = 一套演示

想放一套幻灯片，就在博客里新建一个**页面**（比如 `my-deck.md`），frontmatter 用 `layout: slideshow`，正文是一段段 **`<section class="slide">`**。一段就是一页：

```html
---
layout: slideshow
title: 我的演示
description: 一句话介绍这套演示（会显示在目录卡片上）
---
<section class="slide"><div><h1>第一页</h1></div></section>
<section class="slide"><div><h2>第二页</h2><p>内容...</p></div></section>
```

存好 push 上去，访问这个页面就是一套可放映的演示。多个演示都放在 `_posts` 之外的普通页面里，会自动汇总到 **[幻灯片目录](/slideshows/)**。

> 想要 **Apple 发布会风格**？在 frontmatter 加一句 `style: apple` 即可（黑底、大字号、渐变文字、特性卡片、光晕）。参考 [Apple 风格演示](/apple-deck/)。

## 每页放什么

一个 `<section class="slide">` 里，我会给你一个**居中的幻灯容器**，你往里写内容：

- **大标题**：`<h1>`（最大）、`<h2>`、`<h3>`——字号会自动缩放适配屏幕。
- **正文/列表**：`<p>`、`<ul>/<ol>`——字号/行距也帮你调好了。
- **代码**：`<code>` 会带高亮底。
- **强调**：`<span class="accent">` 会用强调色。

通常我会写 `<section class="slide"><div>...</div></section>`，里面的 `<div>` 用来限制内容宽度，避免文字贴边。**一段只讲一个点**，是最好的幻灯片。

## 目录是怎么来的

右上角 ☰ / 按 `M` 打开的**目录**，是**自动**生成的：它会去抓每一页里的第一个 `h1/h2/h3` 当标题，没有标题就显示"第 N 页"。所以想让目录好看，**每页用一个 h1/h2/h3 开头**就行；再配合 frontmatter 的 `description`，目录网格卡片上就有简介了。

## 一套能用的最小模板

```html
<section class="slide">
  <div>
    <h1>标题</h1>
    <p>副标题或一句话。</p>
  </div>
</section>

<section class="slide">
  <div>
    <h2>要点</h2>
    <ul>
      <li>第一点</li>
      <li>第二点</li>
    </ul>
  </div>
</section>

<section class="slide">
  <div>
    <h2>结束</h2>
    <p class="accent">谢谢。</p>
  </div>
</section>
```

## 放映时的操作

| 操作 | 方式 |
|------|------|
| 开始 | 点封面 · Enter/空格 |
| 翻页 | → / 空格 / 回车 · ← · 点屏幕左右半边 |
| 跳页 | ☰ / `M` 目录里选 |
| 自动播放 | 底部 ▶/⏸（4 秒/页） |
| 全屏 / 明暗 | `F` · `T` |
| 头尾 | `Home` / `End` |
| 页码 + 进度 | 底部 + 顶部进度条 |

## 几个小建议

- **一页一个观点**，别把一页塞满。幻灯片靠"少"取胜。
- **每页用 h1/h2 开头**，目录才好看。
- 标题别太长，屏幕大了缩、小了挤。
- 想换配色/字号，`slide` 里加自己的 class，或在内容的 `<div>` 里内联样式都行。

写多了自然就顺手了。想先在博客里看一套真的，去 **[幻灯片演示](/slideshow-demo/)** 转一圈。
