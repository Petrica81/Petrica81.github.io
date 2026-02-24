---
layout: default
title: Home
---

<section class="hero">
  <div class="kicker">🎮 Game Dev · Portfolio</div>
  <h1>Hi, I’m Petrica.</h1>
  <p>
    I build gameplay prototypes, tools, and small experiments. Here you’ll find my projects, repos, and live demos.
  </p>

  <div class="cta-row">
    <a class="btn primary" href="{{ "/projects" | relative_url }}">See Projects</a>
    <a class="btn" href="{{ "/about" | relative_url }}">About</a>
    <a class="btn" href="https://github.com/Petrica81">GitHub</a>
  </div>
</section>

<h2>Featured</h2>
<p class="muted">A few projects I consider the most representative.</p>

<div class="grid">
{% assign featured = site.data.projects | where: "featured", true %}
{% for p in featured %}
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

<p style="margin-top: 1rem;">
  <a class="btn" href="{{ "/projects" | relative_url }}">View all projects →</a>
</p>
