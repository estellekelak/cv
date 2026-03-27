---
layout: default
title: {{ site.data.cv.infos.nom }} - CV
---

<div class="main-container">

  <!-- COLONNE GAUCHE -->
  <div class="content-left">

    <h2>EXPERIENCES PROFESSIONNELLES</h2>
    {% for exp in site.data.cv.experiences %}
    <div class="block-color-{{ exp.couleur }}_background callout">
      <h3>{{ exp.entreprise | markdownify }}</h3>
      <p><strong>{{ exp.poste | markdownify }}</strong> | {{ exp.dates | markdownify }}</p>

      <details>
        <summary>MISSIONS PRINCIPALES</summary>
        <ul style="margin-top: 10px;">
          {% for m in exp.missions %}
          <li>{{ m | markdownify }}</li>
          {% endfor %}
        </ul>
      </details>
    </div>
    {% endfor %}

    <h2>RÉSULTATS</h2>
    <div class="results-gallery">
      {% for res in site.data.cv.resultats %}
      <div class="result-card">

        <!-- TITRE (année + thématique) -->
        <div class="result-footer">
          <div class="result-year">{{ res.annee | markdownify }}</div>
          <div class="result-separator">—</div>
          <div class="result-theme">{{ res.titre | markdownify }}</div>
        </div>

        <!-- CONTENU -->
        <div class="result-content">
          <ul>
            {% for p in res.points %}
            <li>{{ p | markdownify }}</li>
            {% endfor %}
          </ul>
        </div>

      </div>
      {% endfor %}
    </div>

  </div>

  <!-- SIDEBAR DROITE -->
  <div class="sidebar-right">

    <div class="sidebar-title">Contact</div>
    <div style="font-size: 0.9em; margin-bottom: 30px;">
      <p>✉️ <a href="mailto:{{ site.data.cv.infos.contact.email }}">{{ site.data.cv.infos.contact.email | markdownify }}</a></p>
      <p>📞 {{ site.data.cv.infos.contact.telephone | markdownify }}</p>
      <p>🔗 <a href="https://{{ site.data.cv.infos.contact.linkedin }}">{{ site.data.cv.infos.contact.linkedin | markdownify }}</a></p>
    </div>

    <div class="sidebar-title">Formations</div>
    {% for f in site.data.cv.formations %}
    <div style="border: 1px solid rgba(0,0,0,0.05); padding: 12px; border-radius: 6px; margin-bottom: 12px; font-size: 0.85em;">
      <strong style="display:block;">{{ f.diplome | markdownify }}</strong>
      <span style="display:block; margin-top:4px;">{{ f.etablissement | markdownify }}</span>
      <span style="color: #999;">{{ f.dates | markdownify }}</span>
    </div>
    {% endfor %}

    <div class="sidebar-title">Compétences</div>
    <div style="margin-bottom: 30px;">
      {% for skill in site.data.cv.competences.hard %}
      <code>{{ skill | markdownify }}</code>
      {% endfor %}

      <div style="margin-top: 10px;">
        {% for soft in site.data.cv.competences.soft %}
        <code class="soft-badge">{{ soft | markdownify }}</code>
        {% endfor %}
      </div>
    </div>

    <div class="sidebar-title">Langues</div>
    <div style="font-size: 0.9em; margin-top: 10px;">
      {% for langue in site.data.cv.langues %}
      <p>{{ langue.drapeau }} <strong>{{ langue.nom | markdownify }}</strong> : {{ langue.niveau | markdownify }}</p>
      {% endfor %}
    </div>

    <div class="sidebar-title">Outils</div>
    {% for cat in site.data.cv.categories_outils %}
    <div>
      <p style="font-size: 0.9em; margin-bottom: 5px;">{{ cat.nom | markdownify }}</p>
      <div class="tools-grid" style="padding: 10px; gap: 10px; margin-bottom: 15px;">
        {% for outil in cat.outils %}
        <img src="{{ outil.icone | relative_url }}" class="tool-icon" style="height: 35px; width: auto;" title="{{ outil.nom | markdownify }}">
        {% endfor %}
      </div>
    </div>
    {% endfor %}

  </div>

</div>
