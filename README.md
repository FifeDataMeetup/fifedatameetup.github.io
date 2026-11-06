# Fife Data Meetup website

A simple [Jekyll](https://jekyllrb.com/) site, deployed to GitHub Pages automatically whenever `main` changes.

## ✏️ How to edit (no coding needed)

Everything can be done on github.com: open a file, click the ✏️ pencil icon, make your change, then click **Commit changes**. The site updates within a couple of minutes (check the **Actions** tab).

| I want to…                 | Edit this                   |
|----------------------------|-----------------------------|
| Add a meetup               | add a file in `_events/`    |
| Change the homepage        | `index.md`                  |
| Change the About page      | `about.md`                  |
| Change "Give a Talk"       | `speak.md`                  |
| Change site title or email | `_config.yml`               |

### Adding a meetup

1. Open the `_events` folder and click **Add file → Create new file**.
2. Name it after the year and month, e.g. `2027-01.md`.
3. Paste this in and change the details:

```markdown
---
title: January Meetup
date: 2027-01-14 18:30:00
time: "18:30 – 20:30"
venue: Somewhere, St Andrews
signup: https://link-to-sign-up
---

A short description of the event, talks and speakers.
```

The event appears on the homepage and Events page automatically, and moves to "Past" once the date has gone.
Text uses [Markdown](https://www.markdownguide.org/cheat-sheet/): `## Heading`, `**bold**`, `[link text](https://...)`.

## How it's built

```
_config.yml        site settings and navigation
_events/           one file per meetup
_layouts/event.html  template for event pages
index.md           homepage
events.md          list of upcoming and past events
about.md, speak.md, code-of-conduct.md
.github/workflows/deploy.yml   builds and deploys the site
```

The site uses the plain built-in `minima` theme for now. It rebuilds on every push to `main` and once a day, so past events move across automatically.
One-time setup: **Settings → Pages → Source: GitHub Actions**.
