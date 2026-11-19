---
title: "News"
layout: page
permalink: /allnews.html
---

# News

<div class="section-card" markdown="0">
  <div class="news-timeline">
    {% for article in site.data.news %}
    <article class="news-item">
      <h2 class="news-title">{{ article.headline | escape }}</h2>
      <p class="news-date">{{ article.date | escape }}</p>
      <p class="news-description">{{ article.description | escape }}</p>

      {% if article.links and article.links.size > 0 %}
      <div class="news-links">
        {% for link in article.links %}
        <a href="{{ link.url | escape }}" target="_blank" rel="noopener">{{ link.text | escape }}</a>
        {% endfor %}
      </div>
      {% endif %}
    </article>
    {% endfor %}
  </div>
</div>
