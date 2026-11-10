# Other static sites

The script is not tied to MkDocs. It looks for an index the site already publishes, in this order, starting from the folder of the current page and going up to the site root:

| The site has | The script reads | Typical sites |
| --- | --- | --- |
| A MkDocs search index | `search/search_index.json` | MkDocs, Material for MkDocs |
| A Pagefind index | `pagefind/` | Starlight, and any site built with Pagefind |
| `llms-full.txt` | That file, split at its headings | Sites that publish their docs for AI tools |
| None of these | The text of the page the reader is on | Any page |

Add it with one tag before `</body>`:

```html
<script async src="https://onetagai.com/ask-docs.js" data-key="YOUR_ONETAG_KEY"></script>
```

## Any static site, with Pagefind

[Pagefind](https://pagefind.app) builds a full-text index from the HTML your generator already produced. It works with Hugo, Jekyll, Eleventy, Zola, mdBook and anything else that writes HTML files. Run it after your build:

```bash
npx -y pagefind --site public
```

`public` is the folder with your built site. Add the script tag to your page template, and the box answers from the whole site.

## A site with llms-full.txt

If your site publishes `llms-full.txt` at its root, the script uses it. A file under 20,000 characters is sent whole with each question. A longer one is split at its `#` and `##` headings and searched like any other index.

A line such as `Source: https://example.com/guide/` directly under a heading becomes the link shown under the answer. Without such lines the answer still comes, but without source links.

## One page

With no index at all, the box answers from the page the reader is on. That is enough for a long README-style page, a changelog or an FAQ.

## When the index is somewhere unusual

Tell the script where it is with the `index` option:

```html
<script async src="https://onetagai.com/ask-docs.js"
        data-key="YOUR_ONETAG_KEY" data-index="/docs/search/search_index.json"></script>
```

An address ending in `.json` is read as a MkDocs index, one ending in `.txt` as `llms-full.txt`, and anything else as the folder that contains `pagefind/`.

## Starlight

Starlight has its own package, [starlight-onetag](https://www.npmjs.com/package/starlight-onetag), which puts the question box inside Starlight's search dialog.
