---
layout: default
---

{% include lang.html %}
{% assign df_strftime_m = site.data.locales[lang].df.archives.strftime | default: '/ %m' %}
{% assign df_dayjs_m = site.data.locales[lang].df.archives.dayjs | default: '/ MM' %}

# Jeongil Yang

<p class="fw-light mb-4">Platform Engineer, Developer</p>
<div id="archives" class="pl-xl-3">
  <ul class="list-unstyled">
  {% for profile_summary in site.data.profile_summary %}
    <li>
      {% assign sts = profile_summary.start_date | date: '%s' %}
      <span class="date day" data-ts="{{ sts }}" data-df="DD">{{ profile_summary.start_date | date: '%Y' }}</span>
      <span class="date month small text-muted ms-1" data-ts="{{ sts }}" data-df="{{ df_dayjs_m }}">
        {{ profile_summary.start_date | date: df_strftime_m }}
      </span>

      <span class="me-2">~</span>

      {% assign ets = profile_summary.end_date | date: '%s' %}
      {% assign today = site.time | date: "%Y-%m-%d" %}
      {% assign end_date = profile_summary.end_date | date: "%Y-%m-%d" %}

      {% if today == end_date %}
      <span class="date current"></span>

      {% else %}
      <span class="date day" data-ts="{{ ets }}" data-df="DD">{{ profile_summary.end_date | date: '%Y' }}</span>
      <span class="date month small text-muted ms-1" data-ts="{{ ets }}" data-df="{{ df_dayjs_m }}">
        {{ profile_summary.end_date | date: df_strftime_m }}
      </span>
      {% endif %}

      <a
        {% if profile_summary.link %}
        href="{{ profile_summary.link }}" target="_blank"
        {% else %}
        href="#" onclick="event.preventDefault(); return true;" style="color: inherit; text-decoration: none; cursor: auto;"
        {% endif %}
        >
        {% if profile_summary.image %}<img class="me-2" src="{{ profile_summary.image }}" width="40" height="40" alt="{{ profile_summary.title }}-image" onerror="this.style.display='none'" />{% endif %}
        {{ profile_summary.title }}
        {% if profile_summary.description %} - <span class="small">{{ profile_summary.description }}</span>{% endif %}</a>
    </li>
  {% endfor %}
  </ul>
</div>

## Skills

TBD

## Projects

TBD

## Qualifications

TBD

## Miscellanies

- Started Bouldering (클라이밍) since 2024/11
- Started Golf since 2024/09
