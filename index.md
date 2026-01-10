---
layout: default
title: Home
---

<h1 style="margin-bottom: 0.5rem;">Posts</h1>
<p style="color: var(--muted); margin-bottom: 1.5rem; font-size: 0.95rem;">Things worth reading.</p>

<div class="documents">
{% assign sorted = site.documents | sort: 'date' | reverse %}
{% for doc in sorted %}
  <a href="{{ doc.url | relative_url }}" style="display: block; text-decoration: none; color: inherit; padding: 1rem 0; border-bottom: 1px solid var(--border);">
    <strong style="font-family: Inter, sans-serif; font-size: 1.05rem; color: var(--text); display: block;">{{ doc.title }}</strong>
    {% if doc.description %}<span style="color: var(--muted); font-size: 0.9rem; display: block; margin-top: 0.25rem;">{{ doc.description }}</span>{% endif %}
    {% if doc.date %}<time style="font-family: Inter, sans-serif; font-size: 0.75rem; color: var(--muted); display: block; margin-top: 0.35rem;">{{ doc.date | date: "%B %Y" }}</time>{% endif %}
  </a>
{% endfor %}
</div>

{% if site.documents.size == 0 %}
<p style="color: var(--muted);">No posts yet.</p>
{% endif %}
