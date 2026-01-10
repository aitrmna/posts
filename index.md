---
layout: default
title: Home
---

<h1>Documents</h1>
<p style="color: var(--muted); margin-bottom: 2rem;">A collection of things worth reading.</p>

<div class="documents">
{% assign sorted = site.documents | sort: 'date' | reverse %}
{% for doc in sorted %}
  <article style="margin-bottom: 1.5rem; padding-bottom: 1.5rem; border-bottom: 1px solid var(--border);">
    <h2 style="margin: 0 0 0.25rem;"><a href="{{ doc.url | relative_url }}" style="text-decoration: none;">{{ doc.title }}</a></h2>
    {% if doc.description %}<p style="color: var(--muted); margin: 0; font-size: 0.9rem;">{{ doc.description }}</p>{% endif %}
    {% if doc.date %}<time style="font-family: Inter, sans-serif; font-size: 0.75rem; color: var(--muted);">{{ doc.date | date: "%B %Y" }}</time>{% endif %}
  </article>
{% endfor %}
</div>

{% if site.documents.size == 0 %}
<p style="color: var(--muted);">No documents yet.</p>
{% endif %}
