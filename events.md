---
layout: page
title: Events
permalink: /events/
---

{% assign now = site.time | date: "%s" | plus: 0 %}
{% assign events = site.events | sort: "date" %}
{% assign upcoming_count = 0 %}
{% assign past_count = 0 %}
{% for event in events %}
{% assign event_time = event.date | date: "%s" | plus: 0 %}
{% if event_time >= now %}{% assign upcoming_count = upcoming_count | plus: 1 %}{% else %}{% assign past_count = past_count | plus: 1 %}{% endif %}
{% endfor %}

## Upcoming

{% if upcoming_count > 0 %}
<div class="event-list">
{% for event in events %}
{% assign event_time = event.date | date: "%s" | plus: 0 %}
{% if event_time >= now %}
{% include event-card.html event=event %}
{% endif %}
{% endfor %}
</div>
{% else %}
<p class="muted">No meetups scheduled yet. Check back soon, or <a href="{{ '/speak/' | relative_url }}">offer to give a talk</a> at the next one.</p>
{% endif %}

## Past

{% if past_count > 0 %}
<ul class="past-events">
{% assign past_events = events | reverse %}
{% for event in past_events %}
{% assign event_time = event.date | date: "%s" | plus: 0 %}
{% if event_time < now %}
<li>
  <a class="past-events-thumb" href="{{ event.url | relative_url }}" tabindex="-1" aria-hidden="true">{% if event.image %}<img src="{{ event.image | relative_url }}" alt="" loading="lazy">{% endif %}</a>
  <div>
    <a href="{{ event.url | relative_url }}">{{ event.title }}</a>
    <span class="past-events-date">{{ event.date | date: "%-d %B %Y" }}{% if event.venue %} · {{ event.venue }}{% endif %}</span>
  </div>
</li>
{% endif %}
{% endfor %}
</ul>
{% else %}
<p class="muted">No past meetups yet.</p>
{% endif %}
