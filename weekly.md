---
title: "机场测评周报"
description: "按周更新的机场测速、节点波动、稳定性观察和短周期趋势汇总。"
permalink: /weekly/
---

## 周报列表

<section class="panel">
  {% assign weekly_posts = site.posts | where_exp: "post", "post.categories contains 'weekly'" %}
  {% if weekly_posts.size > 0 %}
    <ul class="post-list">
      {% for post in weekly_posts %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <p>{{ post.description }}</p>
          <p class="muted">{{ post.date | date: "%Y-%m-%d" }}</p>
        </li>
      {% endfor %}
    </ul>
  {% else %}
    <section class="panel">
      <p>这里会自动聚合所有周报文章。新增周报时，文件放进 <code>_posts</code>，并在 front matter 中写上 <code>categories: [reports, weekly]</code> 即可。</p>
    </section>
  {% endif %}
</section>
