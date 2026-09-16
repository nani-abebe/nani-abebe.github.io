# Nani Abebe — portfolio

Personal site built on [al-folio](https://github.com/alshedivat/al-folio), trimmed to an **about** page (bio + news) and a **cv** page.

## Deploy (GitHub Pages)
1. Create a repo named `nani-abebe.github.io` and push this folder to `main`.
2. Repo → Settings → Pages → Source: **GitHub Actions**. The included `.github/workflows/deploy.yml` builds and publishes on every push.
3. Set `url:` in `_config.yml` to `https://nani-abebe.github.io` (leave `baseurl:` blank).

## Edit content
- `_pages/about.md` — bio and the news/social toggles
- `_news/*.md` — one file per news item (`inline: true`)
- `_data/cv.yml` — CV sections; `assets/pdf/cv.pdf` — PDF download button target (path set in `_pages/cv.md`)
- `_data/socials.yml` — email / GitHub / LinkedIn icons
- `assets/img/prof_pic.jpg` — headshot

## Run locally
```
bundle install && bundle exec jekyll serve
```
or `docker compose up` (see `docker-compose.yml`).
