---
layout: default
title: Projects
---

<h1>Projects</h1>
<p class="muted">Click a card to open the project page.</p>
<h2 class="muted">
  I'm actively adding past and current projects — check back soon for more updates.
</h2>
<div class="grid">
{% assign items = site.projects | sort: "year" | reverse %}
{% for p in items %}
  <a class="card-link" href="{{ p.url | relative_url }}">
    <article class="card project">
      <div class="content">
        <div class="title-row">
          <h3>{{ p.title }}</h3>
          {% if p.year %}<div class="small">{{ p.year }}</div>{% endif %}
        </div>

        {% if p.description %}<p>{{ p.description }}</p>{% endif %}

        {% if p.tags and p.tags.size > 0 %}
        <div class="tags">
          {% for t in p.tags %}<span class="tag">{{ t }}</span>{% endfor %}
        </div>
        {% endif %}

        <div class="actions">
          {% if p.live and p.live != "" %}<span class="btn">Live demo</span>{% endif %}
          {% if p.itch and p.itch != "" %}<span class="btn itch">Itch.io</span>{% endif %}
          {% if p.repo and p.repo != "" %}<span class="btn">GitHub repo</span>{% endif %}
        </div>
      </div>

      {% if p.image and p.image != "" %}
      <div class="thumb">
        <img src="{{ p.image | relative_url }}" alt="{{ p.title }} thumbnail" loading="lazy" />
      </div>
      {% endif %}
    </article>
  </a>
{% endfor %}
</div>