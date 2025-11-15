---
layout: default
title: "الرصد العبري اليومي"
permalink: /hebrew-watch/
---

<section class="section">
  <h1 class="page-title">الرصد العبري اليومي — أحدث ما نُشر</h1>
  <p class="page-subtitle">
    هنا يتم تجميع أبرز التقارير العبرية المنشورة ضمن المتابعة اليومية.
  </p>

  {% assign hebrew_posts = site.posts
      | where_exp: "post", "post.categories contains 'israelipress'" %}

  <div class="cards-grid" style="display:grid; gap:20px; margin-top:30px;">

    {% for post in hebrew_posts %}
    <article class="card" style="
        padding:20px;
        border-radius:12px;
        background:#111827;
        border:1px solid #1f2937;
        box-shadow:0 0 10px rgba(0,0,0,0.4);
    ">
      <div class="card-header">
        <h2 class="card-title" style="font-size:20px; margin-bottom:8px;">
          <a href="{{ post.url | relative_url }}" style="color:#ffffff; text-decoration:none;">
            {{ post.title }}
          </a>
        </h2>

        <p class="card-meta" style="color:#9ca3af; font-size:14px;">
          {{ post.date | date: "%Y-%m-%d" }}
        </p>
      </div>

      <p class="card-excerpt" style="margin:15px 0; color:#d1d5db;">
        {{ post.excerpt | strip_html | truncate: 180 }}
      </p>

      <a class="card-link"
         href="{{ post.url | relative_url }}"
         style="color:#60a5fa; font-weight:bold; text-decoration:none;">
         قراءة التقرير كاملاً →
      </a>
    </article>
    {% endfor %}

  </div>
</section>
