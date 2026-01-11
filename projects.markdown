---
layout: page
title: Mes projets
permalink: /projets/
order: 2
description: "Retrouvez mes projets web : intégration de maquettes, sites responsives et autres projets durant ma formation."
---
<!-- Page sommaire des projets -->
# Mes projets réalisés :
<!-- phrase à revoir WARNING -->
<p>Retrouvez quelques-uns de mes projets effectués durant la formation, la prépa et mes projets perso ...</p>
<!-- Bloc des projets -->
<div class="project-grid">
    <!-- Affichage chronologique -->
    <!-- Défini var Jekyll tri_projects dans tous les fichiers du dossier _projects, | passe a la fonction date et inverse lordre -->
     {% assign tri_projects = site.projects | sort: 'date' | reverse %}
     {% for project in tri_projects %} 
     <a href="{{ project.url | relative_url }}" class="card-project">
     <!-- garde la mise en page si pas d image -->
        {% if project.image %}
        <div class="miniature-pj">
            <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
        </div>
        {% endif %}
        <div class="card-pj">
            <h2>{{ project.title }}</h2>
            <!-- truncate : au dela de 100 caractère ça met ... -->
            <p>{{ project.description | truncate: 100 }}</p>
            <!-- Technologies utilisées -->
            <div class="bloc-tech-index">
                {% for tech in project.techs %}
                <span class="tech-index">{{ tech }}</span>
                {% endfor %}
            </div>
        </div>
    <div class="bottom-card-pj">
        <!-- Date du projet -->
        <span class="date-pj">
        {{ project.date | date: "%Y" }}
        </span>
        <span class="txt-icon">Voir le projet 
        <!-- Icone via HeroIcon -->
            <span class="content-icon">
<svg class="icon-arrow" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M17.25 8.25 21 12m0 0-3.75 3.75M21 12H3" /></svg>
            </span>
        </span>
    </div>
    </a>
    {% endfor %}
</div>