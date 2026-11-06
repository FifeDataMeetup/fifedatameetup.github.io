---
layout: page
title: Events
permalink: /events/
---

{% assign now = site.time | date: "%s" | plus: 0 %}
{% assign events = site.events | sort: "date" %}

## Upcoming

<ul>
{% for event in events %}
{% assign event_time = event.date | date: "%s" | plus: 0 %}
{% if event_time >= now %}
<li><a href="{{ event.url | relative_url }}">{{ event.title }}</a> · {{ event.date | date: "%-d %B %Y" }}{% if event.venue %} · {{ event.venue }}{% endif %}</li>
{% endif %}
{% endfor %}
</ul>

## Past

<ul>
{% assign past_events = events | reverse %}
{% for event in past_events %}
{% assign event_time = event.date | date: "%s" | plus: 0 %}
{% if event_time < now %}
<li><a href="{{ event.url | relative_url }}">{{ event.title }}</a> · {{ event.date | date: "%-d %B %Y" }}</li>
{% endif %}
{% endfor %}
</ul>
