---
title: "文章归档"
description: "按年份汇总的机场测评归档页面，方便内部链接和搜索引擎抓取。"
permalink: /archive/
---

## 全部文章归档

{% assign grouped_posts = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in grouped_posts %}
  <section class="panel">
    <h2>{{ year.name }}</h2>
    <ul class="post-list">
      {% for post in year.items %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <p class="muted">{{ post.date | date: "%Y-%m-%d" }} · {{ post.categories | join: " / " }}</p>
        </li>
      {% endfor %}
    </ul>
  </section>
{% endfor %}
