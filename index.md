---
layout: cv
title: CV
---

## EXPÉRIENCES PROFESSIONNELLES
{% for exp in site.data.cv.experiences %}
<div class="callout block-color-{{ exp.couleur }}_background">
  <h3>{{ exp.entreprise }}</h3>
  <p><strong>{{ exp.poste }}</strong> | {{ exp.dates }}</p>

  <details>
    <summary>MISSIONS PRINCIPALES</summary>
    <ul>
      {% for m in exp.missions %}
      <li>{{ m }}</li>
      {% endfor %}
    </ul>
  </details>
</div>
{% endfor %}

## RÉSULTATS
<div class="results-gallery">
{% for res in site.data.cv.resultats %}
  <div class="result-card">
    <div class="result-footer">
      {% if res.annee %}
      <div class="result-year">{{ res.annee }}</div>
      <div class="result-separator">—</div>
      {% endif %}
      <div class="result-theme">{{ res.titre }}</div>
    </div>

    <div class="result-content">
      <ul>
        {% for p in res.points %}
        <li>{{ p }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
{% endfor %}
</div>
