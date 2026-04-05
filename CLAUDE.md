# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is the static website for **thegroovesalad.com**, a pure HTML/CSS site with no build system, no JavaScript framework, and no dependencies. The root domain is a personal landing page; **BeaglePrep** (an Android prepper inventory app, iOS coming soon) lives under `/beagleprep/`.

## Development

Open files directly in a browser — there is no build step, dev server, or package manager. All pages share a single stylesheet (`style.css` at the repo root). Note that root-relative links (`/beagleprep/`, etc.) require a local server or deployed environment to resolve correctly — they won't work via `file://`.

## Structure

```
index.html                    # thegroovesalad.com home (dog photo + project links)
style.css                     # shared styles for all pages
beagleprep/
  index.html                  # BeaglePrep landing page (hero, features, download)
  privacy/
    index.html                # BeaglePrep privacy policy → URL: /beagleprep/privacy/
```

CSS path references are relative (`../style.css`, `../../style.css`) so they work with `file://`. Nav links use root-relative paths (`/beagleprep/`, `/beagleprep/privacy/`).

## Design System

Colors and spacing are controlled via CSS variables in `style.css`:
- `--olive` / `--olive-dark` — primary brand greens (headers, footers, headings)
- `--tan` / `--tan-light` — secondary warm neutrals (background, muted text)
- `--amber` / `--amber-dark` — CTA accent color (buttons, hover states)
- `--radius: 6px` — shared border radius

All pages share the same `<header>` / `<footer>` markup pattern and a small inline `<script>` to set the copyright year dynamically.
