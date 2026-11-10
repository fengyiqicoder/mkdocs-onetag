# How it works

Everything happens in the reader's browser, and only when they ask.

## 1. The index

MkDocs' search plugin writes `search/search_index.json` when it builds your site: the title and the full text of every page, section by section. The search box of your theme uses that file. So does this script.

It is fetched the first time a reader opens the box, not on page load. A reader who never asks downloads nothing extra except the script itself.

## 2. Picking the passages

The question is split into words. Filler words are dropped, `installing` also finds `install`, and names like `mkdocs.yml` stay whole. Chinese, Japanese and Korean have no spaces between words, so they are matched by pairs of neighbouring characters.

Every section of your site gets a score: how often the words occur in it, how rare they are across the site, whether they are in the title, and how much of the question the section covers. The eight best sections go to the AI, each of the top three together with the opening of its page, up to 20,000 characters in all.

If nothing matches, or the question is in Chinese, Japanese or Korean and the docs are not, one short extra request turns the question into search keywords in the language of the docs, and the search runs with those.

## 3. The answer

The question, the passages and the last three exchanges of the conversation go to OneTag AI in one request. The answer streams back and is shown as it arrives. Under it are up to three links to the pages the passages came from.

The last question and its answer are kept in the browser tab (session storage), so a reader who follows one of those links can open the box on the next page and carry on. Closing the tab or pressing **Start over** clears them.

## The instructions

This is what the AI is told, unless you replace it with the `rules` option:

> You are the help desk for this documentation site. Answer only from the pages provided. When the pages cover the question, answer it directly and stop. Only when they do not, say so in one sentence and name the closest page. Under 150 words, no headings. Put commands, code and configuration in a fenced code block, copied the way the pages write them; never invent syntax the pages do not show, and never put ordinary sentences in a code block. Answer in the language of the question.

## What is sent, and where

With each question the browser sends OneTag AI the question, the passages picked from your already public pages, and the conversation so far. Nothing is sent before a reader asks.

OneTag AI does not store questions, passages or answers. It logs token counts, the time, which key was used and the hostname of the site, to count the monthly allowance. The details are in the [privacy page](https://onetagai.com/privacy).

## Where the button comes from

The box and the button are drawn in a shadow root, so your theme's CSS does not change them and theirs does not change your pages. The accent colour is taken from the theme, and the box turns dark when the page is dark.

With Material's instant navigation the header is rebuilt as the reader moves between pages. The script watches for that and puts the button back.
