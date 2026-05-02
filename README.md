# netlify-redirect

A Netlify site that 302-redirects every path to [www.bigconfig.ai](https://www.bigconfig.ai), preserving the path and query string.

For example:

- `/` → `https://www.bigconfig.ai/`
- `/foo/bar?x=1` → `https://www.bigconfig.ai/foo/bar?x=1`

## How it works

The redirect is defined in [`netlify.toml`](./netlify.toml) using Netlify's `[[redirects]]` syntax. `force = true` ensures the redirect fires before any static file lookup; `:splat` carries the path through.

`index.html` is a minimal HTML5 placeholder so Netlify always has a file to publish — the wildcard redirect catches the request before it's served.

## Deploying

Connect this repo to a Netlify site. No build command is needed; the publish directory is the repo root. Pushing to `main` publishes the new config.
