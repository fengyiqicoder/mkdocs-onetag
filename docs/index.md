# Ask AI for MkDocs

A free Ask AI box for MkDocs and Material for MkDocs sites. Readers ask a question in their own words and get an answer written from your pages, with links to the pages it used.

This site runs it. Press **Ask AI** in the header, or ++ctrl+slash++, and try:

- How do I add this to my MkDocs site?
- What does a question cost?
- 可以改按钮的位置吗？

## Add it to your site

One line in `mkdocs.yml`:

```yaml
extra_javascript:
  - https://onetagai.com/ask-docs.js?key=YOUR_ONETAG_KEY
```

Get the key at [onetagai.com](https://onetagai.com/?ref=mkdocs-onetag): one email, no card, 1,000,000 tokens a month. The full steps are on [Install](install.md).

## What you do not need

- **No plugin and no build step.** MkDocs already writes a full-text index of your site to `search/search_index.json`. The box reads that file in the reader's browser.
- **No server and no crawler.** Nothing indexes your site from outside, so there is nothing to keep in sync. When you publish a page, the next question can already use it.
- **No AI provider account.** The key is a OneTag AI key, and it is made to sit in a public page.

## What readers get

- An answer in a few sentences, with commands and configuration in code blocks.
- Up to three links to the pages the answer came from.
- Follow-up questions that remember the conversation.
- Answers in the language of the question, also when the docs are in another one.
- When the AI cannot answer (the monthly allowance is used up, the network is down), the matching pages are still listed, as plain search would.

## Not on MkDocs?

The same script works on Starlight, on any site with a Pagefind index, on any site that publishes `llms-full.txt`, and on a single page. See [Other static sites](other-sites.md).
