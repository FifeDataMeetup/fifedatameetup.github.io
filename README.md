# Fife Data Meetup

Landing site for the Fife Data Meetup, deployed automatically to GitHub Pages.

## How it works

Every push to `main` triggers `.github/workflows/deploy.yml`, which publishes the repo to GitHub Pages.
You can also run it manually from the **Actions** tab ("Run workflow").

## One-time setup

1. Create a repo on GitHub (e.g. `fife-data-meetup`) and push these files to `main`.
2. In the repo go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.
3. Go to the **Actions** tab and watch the "Deploy to GitHub Pages" run (re-run it if it ran before step 2).
4. The site will be live at `https://<your-username>.github.io/fife-data-meetup/`.

## Making changes

Edit `index.html`, commit, push to `main` — the site redeploys in about a minute.
