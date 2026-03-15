# GitHub Pages 机场测评站点

这个仓库已经改造成适合长期发布 Markdown 测评文章的 Jekyll 结构，适用于 GitHub Pages 静态部署。

## 目录结构

```text
.
├─ _config.yml
├─ _layouts/
│  ├─ default.html
│  └─ post.html
├─ _posts/
│  └─ 2026-03-15-v2ray-singbox-airport-review.md
├─ assets/
│  └─ css/style.css
├─ archive.md
├─ index.md
├─ monthly.md
├─ robots.txt
└─ weekly.md
```

## 发布规范

文章统一放到 `_posts/`，文件名格式：

```text
YYYY-MM-DD-slug.md
```

月报 front matter 示例：

```yaml
---
layout: post
title: "2026年4月机场测评月报：V2Ray / Singbox 节点速度与稳定性测试"
description: "2026年4月最新机场测速报告，通过多地区 VPS 实测，对主流机场进行速度、稳定性和价格对比。"
date: 2026-04-15 09:00:00 +0800
author: "newkaiwen92-sudo"
permalink: /monthly/2026/04/v2ray-singbox-airport-review/
categories:
  - reports
  - monthly
tags:
  - 机场测评
  - V2Ray
  - Singbox
  - 月报
keywords: "机场测评,V2Ray 机场,Singbox 机场,机场推荐,节点测速"
report_month: "2026-04"
---
```

周报 front matter 示例：

```yaml
---
layout: post
title: "2026年第16周机场测评周报：节点波动与速度变化"
description: "聚焦一周内机场节点质量变化、速度波动和可用性趋势。"
date: 2026-04-18 09:00:00 +0800
author: "newkaiwen92-sudo"
permalink: /weekly/2026/week-16/airport-review/
categories:
  - reports
  - weekly
tags:
  - 机场测评
  - 周报
  - 节点测速
keywords: "机场周报,节点测速,机场波动,机场可用性"
---
```

## SEO 已做的优化

- 首页、月报页、周报页、归档页已经拆分，利于关键词聚合。
- 文章使用独立 permalink，避免中文文件名导致 URL 混乱。
- 已启用 `jekyll-seo-tag`、`jekyll-sitemap`、`jekyll-feed`。
- 已添加 `robots.txt`，并自动输出 `sitemap.xml` 和 `feed.xml`。
- 首页与文章页都带描述字段，便于搜索引擎摘要抓取。

## GitHub Pages 发布

1. 进入仓库 `Settings > Pages`
2. Source 选择 `Deploy from a branch`
3. Branch 选择 `main`，目录选择 `/ (root)`
4. 保存后等待 Pages 构建完成

站点地址默认会是：

```text
https://newkaiwen92-sudo.github.io/2026_v2ray_singbox_Test/
```
