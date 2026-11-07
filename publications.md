---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

<style>
.publication-card {
  padding: 1.3rem 1.5rem;
  margin-bottom: 1.2rem;
  border: 1px solid var(--global-border-color);
  border-left: 3px solid var(--global-link-color);
  border-radius: 10px;
  background-color: var(--global-bg-color);
  transition: box-shadow 0.2s ease;
}

.publication-card:hover {
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.08);
}

.publication-title {
  font-size: 1.05rem;
  font-weight: 700;
  line-height: 1.4;
  color: var(--global-text-color);
  margin: 0 0 0.5rem;
}

.publication-authors {
  font-size: 0.88rem;
  margin-bottom: 0.6rem;
  line-height: 1.5;
}

.publication-info {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 0.4rem 1rem;
  font-size: 0.8rem;
  margin-top: 0.5rem;
}

.publication-venue {
  color: var(--global-link-color);
  font-weight: 600;
}

.publication-date {
  color: var(--global-text-color);
  opacity: 0.7;
}
</style>

{% assign papers = site.publications | sort: "date" | reverse %}

{% for post in papers %}

<article class="publication-card">

  <h2 class="publication-title">
    {{ post.title | escape }}
  </h2>

  {% if post.authors %}
  <div class="publication-authors">
    {{ post.authors | escape }}
  </div>
  {% endif %}

  <div class="publication-info">

    <span class="publication-venue">
      {{ post.venue | escape }}
    </span>

    <span class="publication-date">
      {{ post.date | date: "%Y" }}
    </span>

  </div>

</article>

{% endfor %}
