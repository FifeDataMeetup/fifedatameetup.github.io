# Fife Data Meetup Website

Official website for Fife Data Meetup

**Temporary URL:** [https://fifedatameetup.github.io/fife-data-meetup-website/](https://fifedatameetup.github.io/fife-data-meetup-website/)

## About

Fife Data Meetup is a free, community-run meetup for anyone interested in data in Fife, Scotland. Each meetup features short talks from the local data community, followed by time to chat and share ideas.

## Tech Stack

This website is built with:
- **Jekyll** - Static site generator (via the `github-pages` gem)
- **Minima** - Default Jekyll theme
- **GitHub Pages** - Hosting platform
- **GitHub Actions** - Builds and deploys the site on every push to `main`

## Project Structure

```
├── .github/workflows/
│   └── deploy.yml           # Build and deploy to GitHub Pages
├── _config.yml              # Jekyll configuration
├── _events/                 # One markdown file per event (YYYY-MM.md)
├── _layouts/
│   └── event.html           # Event page layout
├── assets/
│   └── main.scss            # Site styles (theme colours and overrides)
├── index.md                 # Homepage
├── events.md                # Events listing page
├── about.md                 # About page
├── speak.md                 # Call for speakers
├── code-of-conduct.md       # Code of conduct
└── Gemfile                  # Ruby dependencies for local development
```

## Getting Started

### Prerequisites

- Ruby (version 3.0 or higher)
- Bundler gem

On macOS, the system Ruby is too old. Install a newer version with [Homebrew](https://brew.sh/) (`brew install ruby`) or a version manager such as `rbenv`.

### Installation

1. Clone the repository:
```bash
git clone git@github.com:FifeDataMeetup/fife-data-meetup-website.git
cd fife-data-meetup-website
```

2. Install dependencies:
```bash
bundle install
```

3. Run the development server:
```bash
bundle exec jekyll serve --livereload
```

4. Open your browser and navigate to `http://localhost:4000/fife-data-meetup-website/`

Changes to pages and events reload automatically. Changes to `_config.yml` require restarting the server.

## Adding Content

### Adding a New Event

1. Create a new markdown file in `_events/YYYY-MM.md` (e.g., `_events/2027-01.md`)
2. Use the following frontmatter template, followed by a description of the event:

```yaml
---
title: "Event Title"
date: YYYY-MM-DD HH:MM:SS
time: "18:30 – 20:30"
venue: "Venue name, Town"
signup: https://link-to-signup-page
---

Event description, agenda and speakers.
```

Events are listed as upcoming or past based on their date. The site rebuilds daily so past events move across automatically.

> [!NOTE]
> Quote the `time` value. Unquoted times such as `18:30` can be misread by YAML.

### Editing Pages

Each page is a markdown file in the root of the repository (`index.md`, `about.md`, `speak.md`, `code-of-conduct.md`). Small changes can be made directly on GitHub using the edit (pencil) button.

## Deployment

The site is deployed by GitHub Actions (`.github/workflows/deploy.yml`) on every push to `main`, once a day, and on demand from the Actions tab.

GitHub Pages must be set to deploy from GitHub Actions: **Settings > Pages > Build and deployment > Source: GitHub Actions**.

## Contributing

We welcome contributions! Whether it's fixing typos, improving documentation, or adding new features, please feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-change`)
3. Commit your changes (`git commit -m 'Describe your change'`)
4. Push to the branch (`git push origin feature/my-change`)
5. Open a Pull Request
