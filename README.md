# Site structure

```
_config.yml       site settings (title, URL, plugins)
_layouts/
  default.html    shared HTML shell (nav, <head>, CSS link)
  post.html       wraps default.html, adds title + date for blog posts
_posts/
  YYYY-MM-DD-*.md one file per blog post
assets/css/style.css   your existing CSS, unchanged
index.md          homepage
blog/index.md     blog listing (auto-generated from _posts/)
```

## Run it locally

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000. `jekyll serve` watches for file changes and rebuilds automatically.

## Write a new post

Add a file to `_posts/` named `YYYY-MM-DD-my-post-title.md`:

```markdown
---
title: "My Post Title"
---

Body goes here, in Markdown.
```

That's it — it'll show up on `/blog/` automatically, newest first.

## Deploy on GitHub Pages

1. Push this to your `arhan-14.github.io` repo (or wherever it lives).
2. In the repo: **Settings → Pages → Build and deployment → Source: "Deploy from a branch"**, branch `main`, folder `/ (root)`.
3. GitHub detects `_config.yml` and builds it with Jekyll automatically — no GitHub Actions workflow needed, as long as you only use plugins from GitHub's [supported list](https://pages.github.com/versions/) (the ones in this Gemfile all are).
4. If this repo is NOT named `<username>.github.io` (i.e. it's a project page, not your main user site), set `baseurl: "/your-repo-name"` in `_config.yml` — otherwise leave it as `""`.

## Notes

- `url` in `_config.yml` should match your real GitHub Pages URL (or custom domain if you add a `CNAME` file).
- `jekyll-seo-tag` and `jekyll-feed` are included so you get reasonable `<meta>` tags and an RSS feed (`/feed.xml`) for free — remove them from `_config.yml` and the Gemfile if you don't want them.
