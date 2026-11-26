# HH Timing Help 知识库（help.hhtiming.com）

对 https://help.hhtiming.com/ **全站 145 个子页面**的完整抓取、分析与中文整理，用于任意提问检索回答。

## 目录

| 路径 | 内容 |
|---|---|
| [`digests/INDEX.md`](digests/INDEX.md) | **总索引**：145 页清单（标题 / 原文 URL / 本地源文件） |
| [`digests/overview.md`](digests/overview.md) | 站点总览与章节地图 |
| [`digests/<section>.md`](digests/) | 各章节分析摘要（每页要点 + 常见问答） |
| [`pages/`](pages/) | 每页完整抽取正文（`front-matter` 含 url/title/slug） |
| `digests/sitemap-index.json` | 机器可读页面清单 |

## 章节摘要文件

- `digests/getting-started.md` — 安装、项目、Workspace、Ribbon Bar、Project Tree、官网账号（18 页）
- `digests/workbooks-layouts.md` — 工作簿与布局（3 页）
- `digests/displays.md` — 全部显示屏：Scoreboards / Track maps / Graphing 等（31 页）
- `digests/timing-data-management.md` — 会话数据、实时源、导入导出、回放、Server mode（8 页）
- `digests/settings-options.md` — Backstage / Car / Championship / Track item ghosts（6 页）
- `digests/excel-exports.md` — Live Excel 与 Scoreboard Live Excel（2 页）
- `digests/reporting.md` — 报告制作与查看（3 页）
- `digests/series-specific-info.md` — 25 个赛事系列特殊设置（26 页）
- `digests/timekeeper-specific-info.md` — 12 家计时商对接（12 页）
- `digests/calculation-definitions.md` — 11 项计算公式与口径（11 页）
- `digests/plugins.md` — Drive Time 插件与自研插件（2 页）
- `digests/tips-tricks.md` — 备份、切项目、省屏幕、路由等（6 页）
- `digests/videos-and-notes.md` — 教程视频链接与 Notes（4 页）
- `digests/faq.md` — FAQ 全文问答（2 页）
- `digests/support.md` — 邮件/日志/工程/付款（4 页）
- `digests/whats-new.md` — 版本更新时间线（6 页）

## 如何用它回答问题

1. 先读 `digests/overview.md` 定位章节，或直接在 `digests/*.md` 中搜索关键词。
2. 需要逐字原文、完整选项列表时，按 `digests/INDEX.md` 打开对应 `pages/<slug>.md`。
3. slug 规则：`/a/b/c/` → `a__b__c.md`；首页 → `index.md`。

## 抓取说明

- 来源为站点 `sitemap.xml` 全量 URL（145/145 成功）。
- 正文抽取自各页 Docusaurus `<article>`；截图以路径或 `[内嵌示意图]` 占位。
- 重建脚本：`crawl2.py`（抓取+抽取）、`make_index.py`（总索引）。
