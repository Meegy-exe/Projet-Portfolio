---
layout: page
title: Mes projets
permalink: /projets/
order: 2
---
<!-- Page sommaire des projets -->
# Mes projets réalisés :
<!-- phrase à revoir WARNING -->
### Retrouvez quelques-uns de mes projets effectués durant la formation, la prépa et mes projets perso ...
<!-- Bloc des projets -->
<div class="project-grid">
     {% for project in site.projects %} <a href="{{ project.url | relative_url }}" class="card-project">
     <!-- garde la mise en page si pas d image -->
        {% if project.image %}
        <div class="miniature-pj">
            <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
        </div>
        {% endif %}
        <div class="card-pj">
            <h3>{{ project.title }}</h3>
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
        Voir le projet 
        <!-- Icone via HeroIcon -->
            <span class="content-icon">
<svg class="icon-arrow" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" d="M17.25 8.25 21 12m0 0-3.75 3.75M21 12H3" /></svg>
            </span>
    </div>
    </a>
    {% endfor %}
</div>