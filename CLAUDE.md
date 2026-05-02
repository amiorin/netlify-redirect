# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This repository exists solely to host a Netlify site whose only job is to 302-redirect every path to `https://bigconfig.ai/:splat`. There is no application code, build step, or test suite.

## Configuration

The entire behavior lives in `netlify.toml`. Editing the `[[redirects]]` block changes where traffic goes; `:splat` preserves the original path. `force = true` makes the redirect win over any static file that might otherwise be served.

Deployment is whatever Netlify site this repo is connected to — pushing to the default branch publishes the new config.
