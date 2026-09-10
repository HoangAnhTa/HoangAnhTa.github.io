---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

<p style="color: var(--global-text-color-light); font-size: 1.05em; line-height: 1.6; margin-bottom: 2em;">
  Here are some of the key projects and experiments I have worked on, ranging from software applications and data analysis to system engineering.
</p>

<hr style="border: 0; border-top: 1px solid var(--global-border-color); margin: 2em 0;" />

<div class="projects-list">
  {% assign ordered_projects = site.projects | sort: "date" | reverse %}

  {% for project in ordered_projects %}
    {% if project.url == page.url %}
      {% continue %}
    {% endif %}

    <div class="pub-row" style="display: flex; margin-bottom: 2.5em; position: relative;">
      <div class="pub-image" style="flex: 0 0 160px; margin-right: 1.5em;">
        {% if project.image %}
          <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 10px rgba(0,0,0,0.12); border: 1px solid var(--global-border-color);" />
        {% else %}
          <div style="width: 160px; height: 110px; background: rgba(122,132,136,0.1); border-radius: 8px; display: flex; align-items: center; justify-content: center; font-size: 2.5em;">
            🛠️
          </div>
        {% endif %}
      </div>

      <div class="pub-details" style="flex: 1; min-width: 0;">
        <h3 style="margin: 0 0 0.4em 0; font-size: 1.2em; font-weight: 600;">
          <a href="{{ project.url | relative_url }}" style="color: var(--global-link-color); text-decoration: none;">
            {{ project.title }}
          </a>
        </h3>

        {% if project.excerpt %}
          <p style="margin: 0.3em 0 0.8em 0; font-size: 0.95em; color: var(--global-text-color); line-height: 1.5;">
            {{ project.excerpt }}
          </p>
        {% endif %}

        <div style="display: flex; gap: 0.5em; flex-wrap: wrap;">
          {% if project.github %}
            <a href="{{ project.github }}" target="_blank" style="background: transparent; color: var(--global-text-color); border: 1px solid var(--global-border-color); padding: 0.3em 0.8em; border-radius: 4px; font-size: 0.85em; font-weight: 600; text-decoration: none;">
              GitHub
            </a>
          {% endif %}
          {% if project.demo %}
            <a href="{{ project.demo }}" target="_blank" style="background: var(--global-link-color); color: white; padding: 0.3em 0.8em; border-radius: 4px; font-size: 0.85em; font-weight: 600; text-decoration: none;">
              Live Demo
            </a>
          {% endif %}
        </div>
      </div>
    </div>
  {% else %}
    <p style="color: var(--global-text-color-light); font-style: italic;">
      New projects are currently being documented. Stay tuned!
    </p>
  {% endfor %}
</div>
