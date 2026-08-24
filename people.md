---
layout: default
title: People
permalink: /people/
---

<!-- Banner photo: full lab team under the fall-leaves tree near the building, cropped to faces -->
<div class="hero with-image" style="background-image: url('{{ '/assets/images/banners/team-fall-leaves.jpg' | relative_url }}');">
  <div class="wrap">
    <h1>Meet Our Team</h1>
  </div>
</div>

<div class="wrap">

{% for g in site.data.people %}
<div class="people-group">
  <h2>{{ g.group }}</h2>

  {% assign has_photos = false %}
  {% for m in g.members %}
    {% if m.photo %}{% assign has_photos = true %}{% endif %}
  {% endfor %}

  {% if has_photos %}
  <div class="people-grid">
    {% for m in g.members %}
    <div class="person-card">
      {% if m.photo %}
      <img src="{{ m.photo | relative_url }}" alt="{{ m.name }}">
      {% else %}
      <div class="person-photo-pending" aria-hidden="true">{{ m.name | slice: 0 }}</div>
      {% endif %}
      <div class="person-name">{{ m.name }}</div>
      <div class="person-role">{{ m.role }}</div>
      {% if m.photo == nil %}<div class="person-note">Headshot pending</div>{% endif %}
      {% if m.scholar_url %}<a class="person-link" href="{{ m.scholar_url }}" target="_blank" rel="noopener">{{ m.scholar_label | default: "Google Scholar" }}</a>{% endif %}
    </div>
    {% endfor %}
  </div>
  {% else %}
  <ul class="people-list">
    {% for m in g.members %}
    <li>
      <strong>{{ m.name }}</strong>{% if m.role %} — {{ m.role }}{% endif %}
      {% if m.scholar_url %} · <a href="{{ m.scholar_url }}" target="_blank" rel="noopener">{{ m.scholar_label | default: "Google Scholar" }}</a>{% endif %}
    </li>
    {% endfor %}
  </ul>
  {% endif %}
</div>
{% endfor %}

</div>
