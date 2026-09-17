---
layout: page
permalink: /cv/
title: cv
nav: true
nav_order: 3
description:
---

<script>
document.addEventListener("DOMContentLoaded", function () {
  var h = document.querySelector(".post-title");
  if (h && !h.querySelector(".cv-pdf")) {
    var a = document.createElement("a");
    a.className = "cv-pdf float-right"; a.href = "{{ '/assets/pdf/cv.pdf' | relative_url }}";
    a.target = "_blank"; a.rel = "noopener noreferrer"; a.title = "download CV as PDF";
    a.innerHTML = '<i class="fa-solid fa-file-pdf"></i>';
    h.appendChild(document.createTextNode(" ")); h.appendChild(a);
  }
});
</script>

{% assign cv = site.data.cv.cv %}

## Experience

<div class="cv-timeline">
{% for r in cv.sections.Experience %}
  <div class="cv-row">
    <div class="cv-logo"><img src="https://www.google.com/s2/favicons?domain={{ r.domain }}&sz=128" alt="{{ r.company }} logo" loading="lazy"></div>
    <div class="cv-body">
      <div class="cv-title">{{ r.position }}</div>
      <div class="cv-org">{{ r.company }}{% if r.location %} · {{ r.location }}{% endif %}</div>
    </div>
    <div class="cv-dates">{{ r.start_date | date: "%b %Y" }} – {% if r.end_date == "present" %}Present{% else %}{{ r.end_date | date: "%b %Y" }}{% endif %}</div>
  </div>
{% endfor %}
</div>

## Education

<div class="cv-timeline">
{% for e in cv.sections.Education %}
  <div class="cv-row">
    <div class="cv-logo"><img src="https://www.google.com/s2/favicons?domain={{ e.domain }}&sz=128" alt="{{ e.institution }} logo" loading="lazy"></div>
    <div class="cv-body">
      <div class="cv-title">{{ e.studyType }}, {{ e.area }}</div>
      <div class="cv-org">{{ e.institution }}{% if e.location %} · {{ e.location }}{% endif %}</div>
    </div>
    <div class="cv-dates">{{ e.end_date }}</div>
  </div>
{% endfor %}
</div>

<style>
.post-title .cv-pdf { font-size: inherit; color: inherit; }
.post-title .cv-pdf:hover { text-decoration: none; }
.cv-timeline { display: flex; flex-direction: column; gap: 1.1rem; margin: .75rem 0 2rem; }
.cv-row { display: grid; grid-template-columns: 44px 1fr auto; gap: 0 .9rem; align-items: center; }
.cv-logo img { width: 40px; height: 40px; object-fit: contain; border-radius: 8px; background: #fff; padding: 4px; border: 1px solid rgba(128,128,128,.25); }
.cv-title { font-weight: 600; line-height: 1.25; }
.cv-org { font-size: .9rem; opacity: .75; }
.cv-dates { font-size: .85rem; opacity: .7; white-space: nowrap; text-align: right; }
@media (max-width: 560px) { .cv-row { grid-template-columns: 44px 1fr; } .cv-dates { grid-column: 2; text-align: left; margin-top: .1rem; } }
</style>
