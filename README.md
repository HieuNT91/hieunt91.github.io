# Hieu Trung Nguyen — Academic Website

This is the source for [hieunt91.github.io](https://hieunt91.github.io), a small Jekyll site hosted by GitHub Pages.

## Edit the site

- Edit the biography and awards in `index.md`. Reviewer service is grouped by conference in the `academic_services` front matter; add or remove values from each conference's `years` list as needed.
- Edit profile details and links in `_config.yml`.
- Add or update publications in `_data/publications.yml`. Publications are shown in source order within year groups; records without a `year` appear in a final “Journals” group.
- Add dated updates to `_data/news.yml`. The News section stays hidden while this file is empty.
- Replace `images/HieuNT.jpg` or `resume/Hieu_Resume.pdf` without changing their filenames to keep their public URLs stable.

A publication supports these fields:

```yaml
- title: "Paper title"
  authors: "Author One and Author Two"
  venue: "Conference"
  year: 2026
  note: "Optional distinction"
  paper: "https://example.com/paper"
  code: "https://github.com/example/project"
```

A news item supports these fields:

```yaml
- date: 2026-08-06
  text: "A short update."
  url: "https://example.com/optional-link"
```

## Preview locally

Docker is the recommended preview method. From the repository root, copy and run:

```bash
docker run --rm -it \
  -p 4000:4000 \
  -v "$PWD":/site \
  -v hieunt-jekyll-gems:/usr/local/bundle \
  -w /site \
  ruby:3.1 \
  bash -lc 'gem install bundler --no-document && bundle install && bundle exec jekyll serve --host 0.0.0.0 --port 4000'
```

Open <http://localhost:4000>. Jekyll rebuilds after source files change; refresh the browser to see the result. Press `Ctrl+C` to stop the server.

The first run installs the dependencies. Later runs reuse the `hieunt-jekyll-gems` Docker volume and start faster. Pushing to the repository's publishing branch deploys the site through GitHub Pages.
