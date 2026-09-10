---
layout: archive
title: "Self Learning"
permalink: /self-learning/
author_profile: true
---

<p style="color: var(--global-text-color-light); font-size: 1.05em; line-height: 1.6; margin-bottom: 2em;">
  A structured log of my continuous learning journey—spanning book notes, tutorial write-ups, technical concepts, and personal study insights.
</p>

<hr style="border: 0; border-top: 1px solid var(--global-border-color); margin: 2em 0;" />

<div class="self-learning-list">
  {% assign ordered_notes = site.self_learning | sort: "date" | reverse %}

  {% for note in ordered_notes %}
    {% if note.url == page.url %}
      {% continue %}
    {% endif %}

    <div class="pub-row" style="display: flex; margin-bottom: 2.5em; position: relative;">
      <div class="pub-image" style="flex: 0 0 160px; margin-right: 1.5em;">
        {% if note.image %}
          <img src="{{ note.image | relative_url }}" alt="{{ note.title }}" style="width: 100%; border-radius: 8px; box-shadow: 0 4px 10px rgba(0,0,0,0.12); border: 1px solid var(--global-border-color);" />
        {% else %}
          <div style="width: 160px; height: 110px; background: rgba(122,132,136,0.1); border-radius: 8px; display: flex; align-items: center; justify-content: center; font-size: 2.5em;">
            📖
          </div>
        {% endif %}
      </div>

      <div class="pub-details" style="flex: 1; min-width: 0;">
        <h3 style="margin: 0 0 0.4em 0; font-size: 1.2em; font-weight: 600;">
          <a href="{{ note.url | relative_url }}" style="color: var(--global-link-color); text-decoration: none;">
            {{ note.title }}
          </a>
        </h3>

        {% if note.date %}
          <p style="margin: 0.2em 0 0.5em 0; font-size: 0.85em; color: var(--global-text-color-light);">
            🗓️ {{ note.date | date: "%B %d, %Y" }}
          </p>
        {% endif %}

        {% if note.excerpt %}
          <p style="margin: 0.3em 0 0.8em 0; font-size: 0.95em; color: var(--global-text-color); line-height: 1.5;">
            {{ note.excerpt }}
          </p>
        {% endif %}

        {% if note.tags %}
          <div style="display: flex; gap: 0.4em; flex-wrap: wrap;">
            {% for tag in note.tags %}
              <span style="font-size: 0.8em; padding: 0.2em 0.6em; background: rgba(122,132,136,0.15); border-radius: 12px; color: var(--global-text-color);">
                #{{ tag }}
              </span>
            {% endfor %}
          </div>
        {% endif %}
      </div>
    </div>
  {% else %}
    <p style="color: var(--global-text-color-light); font-style: italic;">
      Learning notes and documentation are being organized. New articles coming soon!
    </p>
  {% endfor %}
</div>
