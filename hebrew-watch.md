---
layout: default
title: "الرصد العبري اليومي"
permalink: /hebrew-watch/
---

# الرصد العبري اليومي — أحدث ما نُشر

هنا يتم تجميع أبرز التقارير العبرية المنشورة ضمن المتابعة اليومية.

{% assign hebrew_posts = site.posts | where_exp: "post", "post.categories contains 'israelipress'" %}

{% for post in hebrew_posts %}
### <a href="{{ post.url | relative_url }}">{{ post.title }}</a>

<p style="color:#94a3b8; font-size:0.9rem;">
  {{ post.excerpt }}
</p>

<hr>
{% endfor %}
