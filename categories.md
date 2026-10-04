---
layout: page
title: 카테고리
permalink: /categories/
---

{% assign category_names = "개발|CTF/Wargame|BugbBounty|블로그/기술문서|논문/컨퍼런스|공모전/자격증" | split: "|" %}
{% assign category_ids = "development|ctf-wargame|bug-bounty|technical-writing|research|competitions-certifications" | split: "|" %}

{% for category in category_names %}
<h2 id="{{ category_ids[forloop.index0] }}">{{ category }}</h2>

{% assign category_posts = site.categories[category] %}
{% if category_posts.size > 0 %}
<ul>
  {% for post in category_posts %}
  <li>
    {{ post.date | date: "%Y-%m-%d" }}
    · <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
  </li>
  {% endfor %}
</ul>
{% else %}
<p>아직 작성된 글이 없습니다.</p>
{% endif %}
{% endfor %}
