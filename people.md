---
layout: default
title: People
permalink: /people/
---

<div class="hero with-image" style="background-image: url('{{ '/assets/images/banners/Team-Laboratory-2.jpg' | relative_url }}');">
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
      <img src="{{ m.photo | relative_url }}" alt="{{ m.name }}">
      <div class="person-name">{{ m.name }}</div>
      <div class="person-role">{{ m.role }}</div>
    </div>
    {% endfor %}
  </div>
  {% else %}
  <ul class="people-list">
    {% for m in g.members %}
    <li><strong>{{ m.name }}</strong>{% if m.role %} — {{ m.role }}{% endif %}</li>
    {% endfor %}
  </ul>
  {% endif %}
</div>
{% endfor %}

</div>
