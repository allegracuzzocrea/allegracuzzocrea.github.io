---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

<style>
.publication-year {
  margin: 2rem 0 1rem;
  padding-bottom: 0.4rem;
  border-bottom: 1px solid var(--global-border-color);
}

.publication-card {
  padding: 1.4rem;
  margin-bottom: 1.2rem;
  border: 1px solid var(--global-border-color);
  border-left: 4px solid var(--global-link-color);
  border-radius: 12px;
  background: var(--global-bg-color);
  box-shadow: 0 3px 12px rgba(0,0,0,0.06);
  transition: transform 0.2s, box-shadow 0.2s;
}

.publication-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(0,0,0,0.12);
}

.publication-title {
  font-size: 1.15rem;
  font-weight: 700;
  line-height: 1.45;
  margin: 0 0 0.5rem;
}

.publication-title a {
  color: var(--global-text-color);
  text-decoration: none;
}

.publication-title a:hover {
  color: var(--global-link-color);
}

.publication-authors {
  font-size: 0.9rem;
  margin-bottom: 0.4rem;
}

.publication-venue {
  font-size: 0.85rem;
  opacity: 0.8;
  margin-bottom: 0.7rem;
}

.publication-summary {
  font-size: 0.9rem;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.publication-links {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.publication-links a {
  display: inline-block;
  padding: 0.4rem 0.8rem;
  border: 1px solid var(--global-link-color);
  border-radius: 6px;
  color: var(--global-link-color);
  text-decoration: none;
  font-size: 0.8rem;
  font-weight: 600;
}

.publication-links a:hover {
  background: var(--global-link-color);
  color: var(--global-bg-color);
}
</style>

<p>
My research publications are listed below.
You can also find my work on
<a href="{{ site.author.googlescholar }}">Google Scholar</a>.
</p>

{% assign papers = site.publications | sort: "date" | reverse %}
{% assign previous_year = "" %}

{% for post in papers %}

{% assign pub_year = post.date | date: "%Y" %}

{% if pub_year != previous_year %}
<h2 class="publication-year">{{ pub_year }}</h2>
{% assign previous_year = pub_year %}
{% endif %}

<article class="publication-card">

  <h3 class="publication-title">
    <a href="{{ post.url | relative_url }}">
      {{ post.title }}
    </a>
  </h3>

  {% if post.authors %}
  <div class="publication-authors">
    {{ post.authors }}
  </div>
  {% elsif post.citation %}
  <div class="publication-authors">
    {{ post.citation }}
  </div>
  {% endif %}

  <div class="publication-venue">
    {% if post.venue %}
      <strong>{{ post.venue }}</strong>
    {% endif %}
    {% if post.status %}
      · {{ post.status }}
    {% endif %}
  </div>

  {% if post.summary %}
  <p class="publication-summary">
    {{ post.summary }}
  </p>
  {% endif %}

  <div class="publication-links">

    <a href="{{ post.url | relative_url }}">Details</a>

    {% if post.paperurl %}
    <a href="{{ post.paperurl }}" target="_blank" rel="noopener">
      PDF
    </a>
    {% endif %}

    {% if post.doi %}
    <a href="https://doi.org/{{ post.doi }}"
       target="_blank" rel="noopener">
      DOI
    </a>
    {% endif %}

    {% if post.codeurl %}
    <a href="{{ post.codeurl }}"
       target="_blank" rel="noopener">
      Code
    </a>
    {% endif %}

  </div>

</article>

{% endfor %}
