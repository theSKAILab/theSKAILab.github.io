---
title: "Publications"
layout: page
permalink: /publications/
---

# Selected Publications

<div markdown="0">
<input type="text" class="pub-search" id="pubSearch" aria-label="Filter publications" placeholder="Filter by title, author, or year...">
</div>

{% capture journal_articles %}{% bibliography --query @article %}{% endcapture %}
{% capture conference_papers %}{% bibliography --query @inproceedings %}{% endcapture %}
{% capture book_chapters %}{% bibliography --query @incollection %}{% endcapture %}

<div class="section-card" id="pubList" markdown="0">

{% if journal_articles contains "pub-entry" %}
<h2>Journal Articles</h2>
{{ journal_articles }}
{% endif %}

{% if conference_papers contains "pub-entry" %}
<h2>Conference and Workshop Papers</h2>
{{ conference_papers }}
{% endif %}

{% if book_chapters contains "pub-entry" %}
<h2>Book Chapters</h2>
{{ book_chapters }}
{% endif %}

</div>