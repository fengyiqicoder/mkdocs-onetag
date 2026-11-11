# FAQ

## Is it safe to put the key in a public page?

Yes. A OneTag AI key can only ask the AI questions, and it has a hard cap. It cannot read anything, and it is not the key of an AI provider account with a bill behind it. If someone copies it, they share your month's allowance. On the Pro plan you can lock the key to your domain.

## Does it work with the built-in MkDocs themes?

Yes. On `mkdocs` and `readthedocs` the button floats in the bottom right corner. On Material for MkDocs it sits in the header next to search.

## Does it work when the site is in a subfolder, like username.github.io/project/?

Yes. The script finds the index relative to the site, not to the domain root.

## Does it work with Material's instant navigation?

Yes. The script loads once, keeps the conversation while the reader moves between pages, and puts its button back when the header is rebuilt.

## Does it work offline or in a site built with use_directory_urls: false?

It works with `use_directory_urls: false`. It does not work from `file://` pages or offline: asking a question needs the network.

## My docs are not in English. Does it work?

Yes. The answer is in the language of the question. Chinese, Japanese and Korean text is matched without needing spaces between words. The box's own text is in English, Simplified Chinese or Traditional Chinese, following the page's language; set `lang` to choose.

## Can I change what the AI is told?

Yes, with the `rules` option. It replaces the default instructions, which are shown on [How it works](how-it-works.md#the-instructions).

## Can I see what readers ask?

No. OneTag AI does not store questions or answers. It only counts the tokens your key uses.

## Why is there a "Powered by OneTag AI" link?

It is how a free service gets found. It is one small line at the bottom of the box.

## Where is the source?

The script is one file, MIT licensed: [ask-docs.js](https://github.com/fengyiqicoder/onetagai/blob/main/sdk/ask-docs.js). This site's source is at [fengyiqicoder/mkdocs-onetag](https://github.com/fengyiqicoder/mkdocs-onetag).
