---
title: "V2Ray / Singbox 机场测评"
description: "专注发布 V2Ray 与 Singbox 机场周报、月报、节点测速与稳定性分析，适合 GitHub Pages 静态发布和搜索引擎收录。"
---

<section class="hero">
  <p class="eyebrow">静态测评站点</p>
  <h1>持续发布 V2Ray / Singbox 机场测评、月报与周报</h1>
  <p>这个站点专门承载你的机场测评 Markdown 文章，适合按月、按周持续发布。结构围绕搜索引擎抓取、长尾关键词覆盖、归档聚合和 GitHub Pages 静态部署设计。</p>
  <div class="hero-grid">
    <div class="metric">
      <strong>{{ site.posts | size }}</strong>
      <span>已发布文章</span>
    </div>
    <div class="metric">
      <strong>{{ site.posts | where_exp: "post", "post.categories contains 'monthly'" | size }}</strong>
      <span>月报文章</span>
    </div>
    <div class="metric">
      <strong>{{ site.posts | where_exp: "post", "post.categories contains 'weekly'" | size }}</strong>
      <span>周报文章</span>
    </div>
  </div>
</section>

## 最新测评

<section class="panel">
  <ul class="post-list">
    {% for post in site.posts limit: 6 %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <p>{{ post.description }}</p>
        <p class="muted">{{ post.date | date: "%Y-%m-%d" }} · {{ post.categories | join: " / " }}</p>
      </li>
    {% endfor %}
  </ul>
</section>

## 内容布局建议

<section class="panel">
  <p>首页负责承接核心关键词，例如“机场测评”“V2Ray 机场推荐”“Singbox 机场测速”“机场月报”。月报页负责覆盖月份关键词，周报页覆盖高频更新关键词，归档页负责增强整站内部链接深度。</p>
  <p>每篇文章建议都包含：报告摘要、测试方法、样本说明、核心排名、详细测评、适合人群、风险提示和相关文章链接。这样对 SEO 和用户阅读都更稳定。</p>
</section>

## 月报入口

<section class="panel">
  <ul class="post-list">
    {% assign monthly_posts = site.posts | where_exp: "post", "post.categories contains 'monthly'" %}
    {% for post in monthly_posts limit: 8 %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <p>{{ post.description }}</p>
      </li>
    {% endfor %}
  </ul>
</section>

## 周报入口

<section class="panel">
  {% assign weekly_posts = site.posts | where_exp: "post", "post.categories contains 'weekly'" %}
  {% if weekly_posts.size > 0 %}
    <ul class="post-list">
      {% for post in weekly_posts limit: 8 %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <p>{{ post.description }}</p>
        </li>
      {% endfor %}
    </ul>
  {% else %}
    <p>周报入口已经预留。后续新增文章时，只要把文章分类设置为 <code>weekly</code>，这里会自动展示。</p>
  {% endif %}
</section>
