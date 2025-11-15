---
layout: default
title: "المتابعة العبرية – تقارير وتحليلات"
---

<section style="max-width: 900px; margin:auto; padding:20px;">

  <h2 style="font-size: 26px; font-weight: bold; margin-bottom: 10px;">
    المتابعة العبرية – أحدث ما نُشر
  </h2>

  <p style="color: #777; margin-bottom: 25px;">
    هنا يتم تجميع أبرز التقارير العبرية المنشورة ضمن المتابعة اليومية.
  </p>

  {% assign hebrew_posts = site.posts | where_exp: "post", "post.categories contains 'israelipress'" %}

  {% for post in hebrew_posts %}
    <article style="background:#111827; padding:20px; border-radius:15px; margin-bottom:20px; border:1px solid #1e293b;">
      <h3 style="font-size:20px; font-weight:600; margin-bottom:8px;">
        <a href="{{ post.url | relative_url }}" style="color:#3b82f6; text-decoration:none;">
          {{ post.title }}
        </a>
      </h3>

      <p style="color:#94a3b8; font-size:14px;">
        {{ post.excerpt }}
      </p>
    </article>
  {% endfor %}

</section>
