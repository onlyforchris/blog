# Chris 的博客

真实工程问题与技术笔记。不做工具清单和概念拼盘。

> 本仓库是 `onlyforchris` 的 GitHub Pages **博客站源码**（Jekyll），托管在
> **[https://onlyforchris.github.io/blog/](https://onlyforchris.github.io/blog/)**。

## 文章

- [《为什么 200 OK 不等于事情做完了》](https://onlyforchris.github.io/blog/why-200-ok-is-not-done/)
- [《一个中文任务名引发的跨平台故障》](https://onlyforchris.github.io/blog/chinese-task-name-transport-failure/)
- [《自动化应该在哪一步停下来让人确认》](https://onlyforchris.github.io/blog/where-to-stop-and-ask-confirmation/)

## 如何写文章

1. 在 [`_posts/`](_posts) 新建 `YYYY-MM-DD-简短标题.md`，采用 frontmatter：

   ```yaml
   ---
   layout: post
   title: 文章标题
   date: 2026-09-01
   tags: [主标签]
   ---
   ```

2. 正文以 `# 标题` 开头，用 `##` / `###` 分节，写完 push 到 `main`，GitHub Pages 会自动构建。

## 资料存档

原先放在本仓库的 Java / 算法 / Python / 软考等**学习资料**已迁移到
[`onlyforchris/notes`](https://github.com/onlyforchris/notes)（`docs`、`pictures` 等也一并迁走），
本仓库只保留博客文章。

## 许可

本项目遵循 [MIT 许可证](LICENSE)。
