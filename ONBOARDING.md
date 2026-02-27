# New Team Member Onboarding Guide

## 1) Codebase Overview
This repository is a **Jekyll blog site** powered by the **Chirpy theme gem**.

- Runtime/theme dependencies are managed in `Gemfile`.
- Most site-level behavior is configured in `_config.yml`.
- Content is written in Markdown under `_posts/`.
- Navigation pages are defined under `_tabs/`.
- Shared UI/metadata settings live in `_data/`.
- A custom plugin in `_plugins/posts-lastmod-hook.rb` updates post `last_modified_at` using git history.

## 2) Main Directory Structure
- `_posts/`: Blog posts. Each file should have front matter such as `title`, `author`, `date`, `categories`, `tags`, and optionally `img_path`.
- `_tabs/`: Static pages for sidebar tabs (`archives`, `categories`, `tags`, `about`).
- `_data/`: YAML data for contact channels, share buttons, authors, and locale labels.
- `_includes/`: Partial templates. Example: utterances comment include.
- `assets/`: Images and favicon assets.
- `_plugins/`: Ruby plugin hooks used during site generation.
- `index.html`: Home layout entry (`layout: home`).
- `_config.yml`: Global site settings (language, timezone, SEO, comments, pagination, permalink defaults, PWA, etc.).

## 3) Important Things to Know Before Editing

### Content conventions
- New posts should follow existing front matter conventions in `_posts/`.
- The default permalink for posts is `/posts/:title/` from `_config.yml`, so title/slug changes affect URLs.
- `author` must map to an entry in `_data/authors.yml`.

### Comments and social links
- Global comments are currently enabled via `utterances` in `_config.yml`.
- Sidebar contacts come from `_data/contact.yml`.
- Post share buttons come from `_data/share.yml`.

### Localization and branding
- Site language is `en` (`_config.yml`), while some content is Korean; UI strings are from `_data/locales/en.yml`.
- Profile/avatar and main branding are configured in `_config.yml` and `assets/img/logo.png`.

### Build/runtime notes
- This repo does **not** include `Gemfile.lock` currently, so local dependency resolution can vary by environment.
- The project excludes several files from Jekyll build output (`_config.yml > exclude`).

## 4) Suggested Learning Path (What to Learn Next)
1. **Jekyll basics**: front matter, collections, layouts, includes.
2. **Chirpy docs**: configuration options for sidebar, comments, PWA, SEO.
3. **Post authoring workflow**: adding posts with consistent categories/tags and image paths.
4. **Release workflow**: local preview (`bundle exec jekyll serve`) and deployment strategy (GitHub Pages or Actions).
5. **Content quality checks**: link checks (`html-proofer`) and basic style conventions.

## 5) First Practical Tasks for a New Member
- Add one sample post with proper front matter and `img_path`.
- Add/adjust one sidebar tab page in `_tabs/`.
- Update one entry in `_data/contact.yml` or `_data/authors.yml`.
- Run local preview and verify comment/share blocks render correctly.
