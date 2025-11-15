---
layout: default
title: "الرصد العبري اليومي"
permalink: /hebrew-watch/
---

<!-- الهيدر التعريفي -->
<section class="card" style="margin-bottom:16px;">
  <div class="card-header">
    <h1 class="card-title">📰 الرصد العبري اليومي</h1>
    <span class="card-tag card-tag--accent">متابعة مستمرة للإعلام العبري</span>
  </div>
  <p class="hero-sub">
    نعرض هنا أبرز ما يرد في الإعلام العبري من تقارير ومقالات تحليلية تتعلق بالشأن الفلسطيني،
    مع متابعة دقيقة من فريق الرصد والتحليل.
  </p>
</section>

{% assign hebrew_posts = site.posts | where_exp: "post", "post.categories contains 'israelipress'" %}

{% if hebrew_posts.size > 0 %}

<!-- قائمة التقارير -->
<section class="grid">
  {% for post in hebrew_posts %}
  <article class="card">
    <div class="card-header">
      <h2 class="card-title">
        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
      </h2>
      <span class="card-tag">
        {{ post.date | date: "%Y-%m-%d" }}
      </span>
    </div>

    <p style="font-size:0.86rem; margin-bottom:10px;">
      {{ post.summary | default: post.excerpt | strip_html | truncate: 160 }}
    </p>

    <a href="{{ post.url | relative_url }}" class="btn btn-ghost">
      قراءة التقرير الكامل →
    </a>
  </article>
  {% endfor %}
</section>

{% else %}

<section class="card">
  <p style="font-size:0.9rem;">
    لا توجد تقارير مصنّفة تحت الفئة <code>israelipress</code> في الوقت الحالي.
    تأكّد أن البوستات العبرية تحتوي على السطر:
  </p>
  <pre><code>categories: ["israelipress"]</code></pre>
</section>

{% endif %}
