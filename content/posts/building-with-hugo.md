---
title: "Building a fast static site with Hugo"
date: 2024-02-01
status: "draft"
summary: "Notes on my experience setting up Hugo with Tailwind CDN."
---

This is an ongoing project to document how I built this site. Hugo is surprisingly fast — full builds take under 100ms even with dozens of posts.

## Why Hugo

I wanted something with no Node.js dependency, no build pipeline, and no JavaScript framework. Hugo is a single binary. You download it, run it, done.

## The setup

The whole theme is a handful of HTML files and Tailwind loaded from a CDN. No `npm install`, no config files beyond `hugo.toml`.
