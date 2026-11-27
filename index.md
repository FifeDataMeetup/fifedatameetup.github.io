---
layout: default
title: Home
---

<div class="intro">
  <h1>Fife Data Meetup</h1>
  <p class="lead">A free, friendly meetup for anyone interested in data in Fife: analysts, engineers, scientists, students and the simply curious. We meet for short talks, conversation and a chance to meet people who do similar work nearby.</p>
</div>

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
<div class="event-list">
{% include event-card.html event=next_event %}
</div>
{% else %}
<p class="muted">No meetup scheduled yet. Check back soon!</p>
{% endif %}

<p><a href="{{ '/events/' | relative_url }}">See all events →</a></p>

## Where and when

We plan to meet roughly once a month in different towns around Fife. Each event page has the exact time and venue.

## Get involved

- **Come along.** Everyone is welcome, whatever your experience.
- **Give a talk.** [Find out more]({{ "/speak/" | relative_url }}).
- **Get in touch.** Email [{{ site.email }}](mailto:{{ site.email }}).
