# Install

## 1. Get a key

Go to [onetagai.com](https://onetagai.com/?ref=mkdocs-onetag), enter your email and open the link you are sent. The key starts with `ot_`. It is free: 1,000,000 tokens, one time, no monthly reset, no card.

The key goes into your page source. That is how it is meant to be used: it can only ask the AI questions and it has a hard cap, so the worst a copied key can do is use up the allowance.

## 2. Add one line to mkdocs.yml

```yaml
extra_javascript:
  - https://onetagai.com/ask-docs.js?key=YOUR_ONETAG_KEY
```

If you already have an `extra_javascript` list, add the line to it.

## 3. Build and look

```bash
mkdocs serve
```

- **Material for MkDocs**: an **Ask AI** button appears in the header, next to the search box.
- **The built-in `mkdocs` and `readthedocs` themes, and other themes**: the button floats in the bottom right corner.

++ctrl+slash++ (++cmd+slash++ on a Mac) opens and closes the box on every theme.

## Keep the search plugin on

The box reads the index that MkDocs' search plugin writes. The plugin is on by default. If you set `plugins:` yourself, keep `search` in the list:

```yaml
plugins:
  - search
```

Without the index the box still works, but it can only answer from the page the reader is on.

## Try it before you have a key

On `localhost` the script works without a key: leave out `?key=...` and it uses a shared demo key. The box says so in a note. On a deployed site a script without a key tells the reader that Ask AI is not set up yet.

## Check that it works

Open your site, press **Ask AI** and ask something your docs answer. You should see an answer and, under it, **Sources** with links to your pages. If you see an error instead, the browser console has a line starting with `[OneTag AI Ask Docs]` and the error code. The codes are listed in the [OneTag AI docs](https://onetagai.com/docs#errors).
