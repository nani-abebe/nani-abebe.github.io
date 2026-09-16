---
layout: book-shelf
title: personal
permalink: /personal/
nav: true
nav_order: 3
collection: books
description:
---

Outside of work, a running log of what I've been reading.

## articles

Pieces I've read recently and keep coming back to.

<ul>
{% for a in site.data.articles %}
  <li>
    <a href="{{ a.url }}" target="_blank" rel="noopener">{{ a.title }}</a>{% if a.source %} · <span class="text-muted">{{ a.source }}</span>{% endif %}{% if a.note %}<br><small>{{ a.note }}</small>{% endif %}
  </li>
{% endfor %}
</ul>

## books

Recent reads, with ratings.
