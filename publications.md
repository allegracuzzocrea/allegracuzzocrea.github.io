---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
<p>
You can also find my publications on
<a href="{{ site.author.googlescholar }}">Google Scholar</a>.
</p>
{% endif %}

{% assign papers = site.publications | sort: "date" | reverse %}

{% for post in papers %}
  {% include archive-single.html %}
{% endfor %}
