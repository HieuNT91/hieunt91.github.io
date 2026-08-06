---
layout: default
title: ""
permalink: /
home: true
academic_services:
  - conference: ICML
    years: [2026, 2025]
  - conference: ICLR
    years: [2026, 2025]
  - conference: WWW
    years: [2025]
  - conference: NeurIPS
    years: [2024]
---

<section class="hero" aria-labelledby="hero-title">
  <div class="hero-portrait-wrap">
    <img class="hero-portrait" src="{{ site.author.avatar | relative_url }}" alt="Portrait of {{ site.author.name }}">
  </div>
  <div class="hero-copy">
    <p class="eyebrow">Academic profile</p>
    <h1 id="hero-title">{{ site.author.name }}</h1>
    <p class="hero-role">{{ site.author.bio }}</p>
    <p class="hero-focus">Reasoning optimization for Transformer-based Language Models.</p>
    <dl class="hero-details">
      <div>
        <dt>Affiliation</dt>
        <dd>{{ site.author.employer }}</dd>
      </div>
      <div>
        <dt>Location</dt>
        <dd>{{ site.author.location }}</dd>
      </div>
    </dl>
    <ul class="hero-actions" aria-label="Profile links">
      <li><a class="button button-primary" href="mailto:{{ site.author.email }}">Email</a></li>
      <li><a class="button" href="{{ site.author.scholar }}">Scholar</a></li>
      <li><a class="button" href="{{ site.author.github }}">GitHub</a></li>
      <li><a class="button" href="{{ site.author.resume | relative_url }}">Résumé</a></li>
    </ul>
  </div>
</section>

<div class="editorial-content">
  <section id="about-me" class="content-section" markdown="1">

  <p class="section-label">01 · Profile</p>
  <h2>About me</h2>

  I am 2nd year PhD student at The Chinese University of Hong Kong (CUHK), advised by [Prof. Viet Anh Nguyen](https://www.vietanhnguyen.net/). Prior to my PhD, I spent 2 wonderful years at VinAI Research as a Research Resident.

  While I have broad experience in recommender systems, graph neural networks, and continual learning, my current research focuses on reasoning optimization for Transformer-based Language Models. I work to improve LLM reasoning performance, diversity, and efficiency using techniques like LLM Post-Training (GRPO, self-distillation), KV Cache Compression, model pruning, and routing.

  I am currently open to internship opportunities and would love to connect. Please feel free to reach out via email ([hilljun.2000@gmail.com](mailto:hilljun.2000@gmail.com)) or WeChat (ID: `junhill9961`).

  </section>

  {% if site.data.news and site.data.news.size > 0 %}
  <section id="news" class="content-section" aria-labelledby="news-title">
    <p class="section-label">02 · Updates</p>
    <h2 id="news-title">News</h2>
    <ul class="news-list">
      {% for item in site.data.news %}
        <li>
          <time datetime="{{ item.date | date: '%Y-%m-%d' }}">{{ item.date | date: '%b %Y' }}</time>
          <span>{% if item.url %}<a href="{{ item.url }}">{{ item.text }}</a>{% else %}{{ item.text }}{% endif %}</span>
        </li>
      {% endfor %}
    </ul>
  </section>
  {% endif %}

  <section id="publications" class="content-section" aria-labelledby="publications-title">
    <p class="section-label">{% if site.data.news and site.data.news.size > 0 %}03{% else %}02{% endif %} · Research</p>
    <h2 id="publications-title">Publications</h2>
    {% assign publication_groups = site.data.publications | group_by: "year" %}
    {% for group in publication_groups %}
      {% if group.name != "" %}
        <div class="publication-group">
          <h3>{{ group.name }}</h3>
          <ol class="publication-list">
            {% for publication in group.items %}
              <li>
                <article class="publication">
                  <p class="publication-title">{{ publication.title }}</p>
                  <p class="publication-authors">{{ publication.authors }}</p>
                  <div class="publication-footer">
                    <p class="publication-meta">
                      <span class="venue-badge">{{ publication.venue }} · {{ publication.year }}</span>{% if publication.note %}<span class="note-badge">{{ publication.note }}</span>{% endif %}
                    </p>
                    {% if publication.paper or publication.code %}
                      <ul class="publication-actions" aria-label="Links for {{ publication.title | escape }}">
                        {% if publication.paper %}<li><a href="{{ publication.paper }}">Paper</a></li>{% endif %}
                        {% if publication.code %}<li><a href="{{ publication.code }}">Code</a></li>{% endif %}
                      </ul>
                    {% endif %}
                  </div>
                </article>
              </li>
            {% endfor %}
          </ol>
        </div>
      {% endif %}
    {% endfor %}
    {% for group in publication_groups %}
      {% if group.name == "" %}
        <div class="publication-group">
          <h3>Journals</h3>
          <ol class="publication-list">
            {% for publication in group.items %}
              <li>
                <article class="publication">
                  <p class="publication-title">{{ publication.title }}</p>
                  <p class="publication-authors">{{ publication.authors }}</p>
                  <div class="publication-footer">
                    <p class="publication-meta">
                      <span class="venue-badge">{{ publication.venue }}</span>{% if publication.note %}<span class="note-badge">{{ publication.note }}</span>{% endif %}
                    </p>
                    {% if publication.paper or publication.code %}
                      <ul class="publication-actions" aria-label="Links for {{ publication.title | escape }}">
                        {% if publication.paper %}<li><a href="{{ publication.paper }}">Paper</a></li>{% endif %}
                        {% if publication.code %}<li><a href="{{ publication.code }}">Code</a></li>{% endif %}
                      </ul>
                    {% endif %}
                  </div>
                </article>
              </li>
            {% endfor %}
          </ol>
        </div>
      {% endif %}
    {% endfor %}
  </section>

  <section id="academic-services" class="content-section" aria-labelledby="academic-services-title">
    <p class="section-label">{% if site.data.news and site.data.news.size > 0 %}04{% else %}03{% endif %} · Community</p>
    <h2 id="academic-services-title">Academic Services</h2>
    <ul class="service-list">
      {% for service in page.academic_services %}
        <li>
          <span class="service-conference">{{ service.conference }}</span>
          <span class="service-years" aria-label="Years">
            {% for year in service.years %}<span>{{ year }}</span>{% endfor %}
          </span>
        </li>
      {% endfor %}
    </ul>
  </section>

  <section id="honors-and-awards" class="content-section" markdown="1">

  <p class="section-label">{% if site.data.news and site.data.news.size > 0 %}05{% else %}04{% endif %} · Recognition</p>
  <h2>Honors and Awards</h2>

  - *2026*: [ICML 2026 Golden Reviewer](https://icml.cc/Conferences/2026/ProgramCommittee).
  - *July 2024*: ICLR2026 Travel Grant! (Rio de Janeiro, Brazil)
  - *July 2024*: ICML2024 Travel Grant! (Vienna, Austria)
  - *April 2022*: Bachelors Thesis with highest score.
  - *September 2018 - April 2022*: Honor Student Scholarship for all Academic Years - UIT

  </section>
</div>
