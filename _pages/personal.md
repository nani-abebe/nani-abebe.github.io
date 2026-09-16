---
layout: page
title: personal
permalink: /personal/
nav: true
nav_order: 3
description:
---

Outside of work, a running log of what I've been reading.

## books

<div class="book-grid">
{% assign books = site.books | sort: "finished" | reverse %}
{% for b in books %}
  <div class="book-card">
    <a href="{{ b.url | relative_url }}">
      <img alt="{{ b.title }} cover" src="{% if b.cover %}{{ b.cover | relative_url }}{% elsif b.isbn %}https://covers.openlibrary.org/b/isbn/{{ b.isbn | remove: '-' }}-L.jpg?default=false{% elsif b.olid %}https://covers.openlibrary.org/b/olid/{{ b.olid }}-L.jpg?default=false{% endif %}" loading="lazy">
    </a>
    <div class="book-title">{{ b.title }}</div>
    <div class="book-author">{{ b.author }}</div>
    <div class="book-stars" title="{{ b.stars }}/5">{% for i in (1..5) %}{% if i <= b.stars %}★{% else %}☆{% endif %}{% endfor %}</div>
  </div>
{% endfor %}
</div>

## articles

Pieces I've read recently and keep coming back to.

<ul class="article-list">
{% for a in site.data.articles %}
  <li>
    <a href="{{ a.url }}" target="_blank" rel="noopener">{{ a.title }}</a>{% if a.source %} <span class="text-muted">· {{ a.source }}</span>{% endif %}{% if a.note %}<br><small class="text-muted">{{ a.note }}</small>{% endif %}
  </li>
{% endfor %}
</ul>

<style>
.book-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(140px, 1fr)); gap: 1.5rem 1rem; margin: 1rem 0 2rem; }
.book-card { text-align: center; }
.book-card img { width: 100%; max-width: 140px; aspect-ratio: 2/3; object-fit: cover; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,.18); transition: transform .15s; }
.book-card a:hover img { transform: translateY(-3px); }
.book-title { font-weight: 600; font-size: .9rem; margin-top: .5rem; line-height: 1.2; }
.book-author { font-size: .8rem; opacity: .7; }
.book-stars { color: #e0a800; letter-spacing: 1px; font-size: .95rem; margin-top: .15rem; }
.article-list li { margin-bottom: .6rem; }
</style>
