---
layout: default
title: {{ site.data.cv.infos.nom }} - CV
---

<div class="main-container">

  <div class="content-left">
    <h2>EXPERIENCES PROFESSIONNELLES</h2>
    {% for exp in site.data.cv.experiences %}
    <div class="block-color-{{ exp.couleur }}_background callout">
      <h3>{{ exp.entreprise }}</h3>
      <p><strong>{{ exp.poste }}</strong> | {{ exp.dates }}</p>
      <details>
        <summary>MISSIONS PRINCIPALES</summary>
        <ul style="margin-top: 10px;">
          {% for m in exp.missions %}<li>{{ m }}</li>{% endfor %}
        </ul>
      </details>
    </div>
    {% endfor %}

    <h2>RÉSULTATS</h2>
    <div class="results-gallery">
      {% for res in site.data.cv.resultats %}
      <div class="result-card">
        <div class="result-content">
          <ul>{% for p in res.points %}<li>{{ p }}</li>{% endfor %}</ul>
        </div>
        <div class="result-footer">
          <strong>{{ res.titre }}</strong>
          <small>{{ res.date }}</small>
        </div>
      </div>
      {% endfor %}
    </div>

    </div>


  <div class="sidebar-right">
    <div class="sidebar-title">Contact</div>
    <div style="font-size: 0.9em; margin-bottom: 30px;">
      <p>✉️ <a href="mailto:{{ site.data.cv.infos.contact.email }}">{{ site.data.cv.infos.contact.email }}</a></p>
      <p>📞 {{ site.data.cv.infos.contact.telephone }}</p>
      <p>🔗 <a href="https://{{ site.data.cv.infos.contact.linkedin }}">LinkedIn</a></p>
    </div>
    
    <div class="sidebar-title">Formations</div>
    {% for f in site.data.cv.formations %}
    <div style="border: 1px solid rgba(0,0,0,0.05); padding: 12px; border-radius: 6px; margin-bottom: 12px; font-size: 0.85em;">
      <strong style="color: #2383e2; display: block;">{{ f.diplome }}</strong>
      <span style="display:block; margin-top:4px;">{{ f.etablissement }}</span>
      <span style="color: #999;">{{ f.dates }}</span>
    </div>
    {% endfor %}

    <div class="sidebar-title">Compétences</div>
    <div style="margin-bottom: 30px;">
      {% for skill in site.data.cv.competences.hard %}<code>{{ skill }}</code>{% endfor %}
      <div style="margin-top: 10px;">
        {% for soft in site.data.cv.competences.soft %}<code class="soft-badge">{{ soft }}</code>{% endfor %}
      </div>
    </div>

    <div class="sidebar-title">Langues</div>
    <div style="font-size: 0.9em; margin-top: 10px;">
      {% for langue in site.data.cv.langues %}
      <p>{{ langue.drapeau }} **{{ langue.nom }}** : {{ langue.niveau }}</p>
      {% endfor %}
    </div>

    <div class="sidebar-title">Outils</div>
    {% for cat in site.data.cv.categories_outils %}
    <div>
        <p style="font-size: 0.9em; margin-bottom: 5px;">{{ cat.nom }}</p>
        <div class="tools-grid" style="padding: 10px; gap: 10px; margin-bottom: 15px;">
            {% for outil in cat.outils %}
            <img src="{{ outil.icone | relative_url }}" class="tool-icon" style="height: 35px; width: auto;" title="{{ outil.nom }}">
            {% endfor %}
        </div>
    </div>
    {% endfor %}
  </div>

</div>