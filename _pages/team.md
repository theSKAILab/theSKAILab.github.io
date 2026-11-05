---
title: "Team"
layout: page
permalink: /team/
---
<h1 class="page-title-hidden">Team</h1>

{% assign director = site.data.director %}

{% if director %}
## Lab Director

<div class="section-card team-director-card" markdown="0">
<div class="pi-card">

<div class="director-text">
<h3 class="pi-name">{{ director.name | escape }}</h3>

<p>
{{ director.title | escape }}<br>
{{ director.leadership | escape }}, <a href="{{ director.leadership_url | escape }}">{{ director.leadership_unit | escape }}</a><br>
{{ director.affiliation | escape }}<br>
{{ director.institution | escape }}
</p>

<p>Torsten’s research focuses on spatial informatics, knowledge representation, and automated reasoning, with an emphasis on geospatial ontologies. He joined the University of Maine in 2013 and previously worked as a postdoctoral researcher with Autodesk Research.</p>

{% if director.education.size > 0 %}
<ul style="margin-top: var(--space-4);">
{% for education in director.education %}
<li>{{ education | escape }}</li>
{% endfor %}
</ul>
{% endif %}

{% if director.email_display and director.email_display != "" %}
<p>{{ director.email_display | escape }}</p>
{% endif %}
</div>

<div class="director-media">
{% if director.photo and director.photo != "" %}
<img src="{{ director.photo | prepend: '/images/' | relative_url }}" class="pi-photo" alt="{{ director.name | escape }}" width="160" height="160">
{% endif %}

<div class="pi-links">
{% if site.links.google_scholar and site.links.google_scholar != "" %}
<a href="{{ site.links.google_scholar | escape }}" class="chip">Google Scholar</a>
{% endif %}
{% if site.links.researchgate and site.links.researchgate != "" %}
<a href="{{ site.links.researchgate | escape }}" class="chip">ResearchGate</a>
{% endif %}
{% if director.orcid and director.orcid != "" %}
<a href="{{ director.orcid | escape }}" class="chip">ORCID</a>
{% endif %}
</div>
</div>

</div>
</div>
{% endif %}

{% if site.data.team_members.size > 0 %}
## Research Assistants
<div class="team-grid" markdown="0">
{% for member in site.data.team_members %}
<div class="team-card">
{% if member.photo and member.photo != "" %}
<img src="{{ member.photo | prepend: '/images/' | relative_url }}" class="team-photo" alt="{{ member.name | escape }}" width="100" height="100" loading="lazy">
{% else %}
{% assign name_parts = member.name | strip | split: " " %}
<div class="team-photo team-photo-initials" aria-hidden="true">
{{ name_parts.first | slice: 0, 1 | upcase }}{% if name_parts.size > 1 %}{{ name_parts.last | slice: 0, 1 | upcase }}{% endif %}
</div>
{% endif %}
<h3 class="team-name">{{ member.name | escape }}</h3>
{% if member.role and member.role != "" %}
<p class="team-info"><strong>{{ member.role | escape }}</strong></p>
{% endif %}
{% if member.info and member.info != "" %}
<p class="team-info">{{ member.info }}</p>
{% endif %}
<div class="team-links">
{% if member.profile and member.profile != "" %}
<a href="{{ member.profile | escape }}" class="chip">Website</a>
{% endif %}
{% if member.orcid and member.orcid != "" %}
<a href="{{ member.orcid | escape }}" class="chip">ORCID</a>
{% endif %}
</div>
</div>
{% endfor %}
</div>

{% endif %}

{% if site.data.alumni.size > 0 %}
## Former Lab Members

<div class="section-card team-former-card" markdown="0">
<table class="alumni-table">
<thead>
<tr>
<th scope="col">Name</th>
<th scope="col">Role</th>
<th scope="col">Degree Earned</th>
<th scope="col">Current Position</th>
</tr>
</thead>
<tbody>
{% for member in site.data.alumni %}
<tr>
<td>{{ member.name | escape }}</td>
<td>{{ member.role | escape }}{% if member.duration and member.duration != "" %} ({{ member.duration | escape }}){% endif %}</td>
<td>{{ member.degree | escape }}</td>
<td>{{ member.info | escape }}</td>
</tr>
{% endfor %}
</tbody>
</table>
</div>

{% endif %}