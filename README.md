# Chris 的博客

真实工程问题与技术笔记。不做工具清单和概念拼盘。

> 本仓库是 `onlyforchris` 的 GitHub Pages **博客站源码**（Jekyll），托管在
> **[https://onlyforchris.github.io/blog/](https://onlyforchris.github.io/blog/)**。

## 文章

- [幂等：IM webhook 重试时，怎么保证不重复处理](https://onlyforchris.github.io/blog/idempotency-for-webhook-retries/)
- [SQLite 当控制面存储，够用但边界在哪](https://onlyforchris.github.io/blog/sqlite-for-control-plane/)
- [渠道验签差异，是接入的隐性成本](https://onlyforchris.github.io/blog/channel-signature-cost/)
- [9 个 IM 渠道，怎么收敛成一套接入接口](https://onlyforchris.github.io/blog/unify-nine-im-channels/)
- [为什么把 cron 放在宿主进程里，而不是独立服务](https://onlyforchris.github.io/blog/cron-in-host-process/)
- [Markdown 到公众号草稿，样式映射里最容易坏的一环](https://onlyforchris.github.io/blog/markdown-to-wechat-styling/)
- [把"符合"拆成四档，而不是非黑即白](https://onlyforchris.github.io/blog/tiers-instead-of-binary/)
- [中文技术标书的"五段式"，和"强承诺一定要补边界"](https://onlyforchris.github.io/blog/five-part-bid-and-boundaries/)
- [一个本地控制面的边界：MCP 工具该暴露多细](https://onlyforchris.github.io/blog/local-control-plane-boundaries/)
- [《为什么 200 OK 不等于事情做完了》](https://onlyforchris.github.io/blog/why-200-ok-is-not-done/)
- [《一个中文任务名引发的跨平台故障》](https://onlyforchris.github.io/blog/chinese-task-name-transport-failure/)
- [《自动化应该在哪一步停下来让人确认》](https://onlyforchris.github.io/blog/where-to-stop-and-ask-confirmation/)

另有[关于页](https://onlyforchris.github.io/blog/about/)与[标签页](https://onlyforchris.github.io/blog/tags/)。

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
