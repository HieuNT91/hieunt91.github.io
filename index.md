---
layout: default
title: ""
permalink: /
---

<section id="about-me" markdown="1">

<h1>About me</h1>

I am 2nd year PhD student at The Chinese University of Hong Kong (CUHK), advised by [Prof. Viet Anh Nguyen](https://www.vietanhnguyen.net/). Prior to my PhD, I spent 2 wonderful years at VinAI Research as a Research Resident.

While I have broad experience in recommender systems, graph neural networks, and continual learning, my current research focuses on reasoning optimization for Transformer-based Language Models. I work to improve LLM reasoning performance, diversity, and efficiency using techniques like LLM Post-Training (GRPO, self-distillation), KV Cache Compression, model pruning, and routing.

I am currently open to internship opportunities and would love to connect. Please feel free to reach out via email ([hilljun.2000@gmail.com](mailto:hilljun.2000@gmail.com)) or WeChat (ID: `junhill9961`).

</section>

{% if site.data.news and site.data.news.size > 0 %}
<section id="news">
  <h1>News</h1>
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

<section id="publications">
  <h1>📜 Publications</h1>
  <ol class="publication-list">
    {% for publication in site.data.publications %}
      <li>
        <span class="publication-title">{{ publication.title }}</span>, with {{ publication.authors }}.
        <span class="publication-meta">{{ publication.venue }}{% if publication.year %} {{ publication.year }}{% endif %}{% if publication.note %} ({{ publication.note }}){% endif %}.</span>
        {% if publication.paper or publication.code %}
          <span class="publication-links">
            {% if publication.paper %}<a href="{{ publication.paper }}">Paper</a>{% endif %}{% if publication.paper and publication.code %} · {% endif %}{% if publication.code %}<a href="{{ publication.code }}">Code</a>{% endif %}
          </span>
        {% endif %}
      </li>
    {% endfor %}
  </ol>
</section>

<section id="academic-services" markdown="1">

<h1>📜 Academic Services</h1>

I served as a reviewer for some reputable conferences: ICML2026, ICLR2026, ICML2025, ICLR2025, WWW2025, NeurIPS2024.

</section>

<section id="honors-and-awards" markdown="1">

<h1>🏵️ Honors and Awards</h1>

- *July 2024*: ICLR2026 Travel Grant! (Rio de Janeiro, Brazil)
- *July 2024*: ICML2024 Travel Grant! (Vienna, Austria)
- *April 2022*: Bachelors Thesis with highest score.
- *September 2018 - April 2022*: Honor Student Scholarship for all Academic Years - UIT

</section>
