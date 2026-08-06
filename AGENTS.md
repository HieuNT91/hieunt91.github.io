# Repository Guide

## Purpose

This repository contains a deliberately small personal academic website built with Jekyll and deployed through GitHub Pages. Preserve the minimal, locally owned implementation unless a task explicitly calls for a larger framework or theme.

## Structure

- `index.md`: biography, academic services, awards, and Liquid rendering for repeatable content.
- `_data/publications.yml`: ordered publication records.
- `_data/news.yml`: dated news records; an empty list hides the section and navigation link.
- `_config.yml`: site metadata, profile details, and external profile links.
- `_layouts/default.html`: the complete page shell and profile/navigation markup.
- `assets/css/main.css`: all responsive and print styling; the site intentionally has no JavaScript.
- `images/HieuNT.jpg` and `resume/Hieu_Resume.pdf`: public assets whose filenames are stable URLs.

## Editing Rules

- Keep biography and service prose in `index.md`; do not duplicate it in configuration or data files.
- Add publications with `title`, `authors`, `venue`, and optional `year`, `note`, `paper`, and `code` fields.
- Add news with `date`, `text`, and optional `url` fields.
- Preserve `/images/HieuNT.jpg` and `/resume/Hieu_Resume.pdf` unless a task explicitly includes a URL migration.
- Keep internal URLs compatible with `baseurl` by using Jekyll's `relative_url` or `absolute_url` filters in templates.
- Do not reintroduce Academic Pages demo content, vendored themes, generated notebooks, icon-font bundles, npm tooling, or JavaScript without a concrete requirement.
- Do not commit `_site`, Jekyll caches, Bundler output, or `Gemfile.lock`; these are ignored build artifacts.
- Maintain keyboard focus styles, semantic landmarks, image alt text, and the mobile breakpoints when changing layout or CSS.

## Preview and Validation

Use the copyable Docker preview command in `README.md`, then open <http://localhost:4000>.

Before handing off changes:

1. Run a Jekyll build with `--strict_front_matter`.
2. Confirm the homepage and `/404.html` build successfully.
3. Confirm all publication records render and optional links do not leave empty separators.
4. Confirm News remains absent when `_data/news.yml` is `[]` and appears after adding an entry.
5. Run `git diff --check` and ensure generated artifacts remain untracked.
