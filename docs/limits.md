# Limits and cost

## What it costs

Nothing on the free plan: a OneTag AI key comes with 1,000,000 tokens, one time, no monthly reset. It is a one-time allowance with no monthly reset.

A question uses tokens for the passages sent with it and for the answer. The passages are the larger part: up to 20,000 characters of your pages go with each question, and the answer is capped at 500 tokens. On this site a question costs 1,000 to 3,000 tokens; the most one can cost is about 6,000. The free allowance is therefore good for roughly 300 to 1,000 questions a month.

One key works on any number of sites, and they share its allowance.

## When the allowance runs out

The box tells the reader that the site has used up its AI allowance, and lists the pages that match the question. Readers still get to the right page; they only lose the written answer until the 1st.

If your site needs more, the Pro plan is $9.9 a month for 100,000,000 tokens. Pro keys can also be locked to your domain, so a copied key does not work anywhere else. Both are set up from the [dashboard](https://onetagai.com/?ref=mkdocs-onetag).

## Request limits

- 20 questions a minute from one reader (one IP address).
- 60 questions a minute on one key.

Over the limit, the box asks the reader to wait a moment.

## What it does not do

- **It does not know anything outside your pages.** The AI is told to answer only from the passages it is given, and to say so when they do not cover the question.
- **It finds passages by words, not by meaning.** A question that uses none of the words in your docs gets one rewrite into search keywords. If that finds nothing either, the answer is written from the page the reader is on.
- **It reads what the search index holds.** Pages excluded from search are not in the index, so they are not used.
- **Very large sites load a large index.** The index is the same file your theme's search loads. On a site with thousands of pages it can be several megabytes; it is fetched once, when the reader first opens the box.
- **Answers can be wrong.** The source links under each answer are there so readers can check.
