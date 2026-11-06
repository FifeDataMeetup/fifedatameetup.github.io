---
layout: default
title: Home
---

# Fife Data Meetup

A free, friendly meetup for anyone interested in data in Fife: analysts, engineers, scientists, students and the simply curious. We meet for short talks, conversation and a chance to meet people who do similar work nearby.

{% assign now = site.time | date: "%s" | plus: 0 %}
{% assign next_event = nil %}
{% assign events = site.events | sort: "date" %}
{% for event in events %}
{% assign event_time = event.date | date: "%s" | plus: 0 %}
{% if event_time >= now %}
{% assign next_event = event %}
{% break %}
{% endif %}
{% endfor %}

## Next meetup

{% if next_event %}
**[{{ next_event.title }}]({{ next_event.url | relative_url }})**  
📅 {{ next_event.date | date: "%A %-d %B %Y" }}{% if next_event.time %} · {{ next_event.time }}{% endif %}  
📍 {{ next_event.venue }}
{% else %}
No meetup scheduled yet. Check back soon!
{% endif %}

[See all events →]({{ "/events/" | relative_url }})

## Where and when

We plan to meet roughly once a month in different towns around Fife. Each event page has the exact time and venue.

## Get involved

- **Come along.** Everyone is welcome, whatever your experience.
- **Give a talk.** [Find out more]({{ "/speak/" | relative_url }}).
- **Get in touch.** Email [{{ site.email }}](mailto:{{ site.email }}).
