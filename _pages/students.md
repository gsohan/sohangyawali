---
layout: page
permalink: /students/
title: students
description: Current and former graduate/undergraduate students
nav: true
nav_order: 4
display_categories: [Current, Alumni]
horizontal: false
---

<div class="students">

{% assign current = site.data.students | where: "status", "current" %}
{% assign alumni = site.data.students | where: "status", "alumni" %}

{% if current.size > 0 %}
<h3>Current Students</h3>
<div class="row row-cols-1 row-cols-md-2 g-4 mb-4">
  {% for s in current %}
  <div class="col">
    <div class="card h-100 p-3">
      <div class="row g-0">
        <div class="col-4">
          {% if s.photo %}
          <img src="{{ '/assets/img/' | append: s.photo | relative_url }}" class="img-fluid rounded-circle" alt="{{ s.name }}">
          {% endif %}
        </div>
        <div class="col-8">
          <div class="card-body py-0">
            <h5 class="card-title mb-0">{{ s.name }}</h5>
            <p class="text-muted mb-1"><em>{{ s.role }}</em></p>
            <p class="card-text small">{{ s.bio }}</p>
            <p class="small">
              {% if s.email %}<a href="mailto:{{ s.email }}"><i class="fas fa-envelope"></i></a>{% endif %}
              {% if s.website %}&nbsp;<a href="{{ s.website }}" target="_blank"><i class="fas fa-globe"></i></a>{% endif %}
              {% if s.github %}&nbsp;<a href="https://github.com/{{ s.github }}" target="_blank"><i class="fab fa-github"></i></a>{% endif %}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

{% if alumni.size > 0 %}
<h3>Alumni</h3>
<div class="row row-cols-1 row-cols-md-2 g-4">
  {% for s in alumni %}
  <div class="col">
    <div class="card h-100 p-3">
      <div class="row g-0">
        <div class="col-4">
          {% if s.photo %}
          <img src="{{ '/assets/img/' | append: s.photo | relative_url }}" class="img-fluid rounded-circle" alt="{{ s.name }}">
          {% endif %}
        </div>
        <div class="col-8">
          <div class="card-body py-0">
            <h5 class="card-title mb-0">{{ s.name }}</h5>
            <p class="text-muted mb-1"><em>{{ s.role }}</em></p>
            <p class="card-text small">{{ s.bio }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

</div>
