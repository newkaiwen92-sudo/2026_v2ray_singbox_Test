---
title: "机场测评月报"
description: "按月归档的 V2Ray 与 Singbox 机场测速和稳定性测评，方便搜索引擎抓取每月报告。"
permalink: /monthly/
---

## 月报列表

<section class="panel">
  <ul class="post-list">
    {% assign monthly_posts = site.posts | where_exp: "post", "post.categories contains 'monthly'" %}
    {% for post in monthly_posts %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <p>{{ post.description }}</p>
        <p class="muted">{{ post.date | date: "%Y-%m-%d" }}</p>
      </li>
    {% endfor %}
  </ul>
</section>
