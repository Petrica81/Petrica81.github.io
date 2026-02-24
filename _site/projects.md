---
layout: default
title: Projects
---

<h1>Projects</h1>
<p class="muted">Repositories, demos, and experiments.</p>

<div class="grid">
{% for p in site.data.projects %}
  <article class="card">
    <div class="title-row">
      <h3>{{ p.name }}</h3>
      {% if p.year %}<div class="small">{{ p.year }}</div>{% endif %}
    </div>

    <p>{{ p.description }}</p>

    {% if p.tags and p.tags.size > 0 %}
    <div class="tags">
      {% for t in p.tags %}<span class="tag">{{ t }}</span>{% endfor %}
    </div>
    {% endif %}

    <div class="actions">
      {% if p.live and p.live != "" %}<a class="btn" href="{{ p.live }}">Live demo</a>{% endif %}
      {% if p.repo and p.repo != "" %}<a class="btn" href="{{ p.repo }}">GitHub repo</a>{% endif %}
    </div>
  </article>
{% endfor %}
</div>
