---
name: x-tweet-search-by-query
description: "Find publicly indexed X (Twitter) posts matching handles, brands, keywords, hashtags, and date ranges using Glean web search. Summarize sentiment, themes, questions, complaints, praise, and response opportunities with citations. Does not require Browser Act, an X login, or an API key."
---

# Public X Social Listening in Glean

Find and analyze public X posts with Glean's available web-search capability. Do not require Browser Act, a logged-in X session, cookies, an X API key, or local scripts.

## Scope and boundaries

Use this skill for public-web social listening: brand or handle mentions, discussions indexed by search engines, campaign and hashtag monitoring, competitor research, and sentiment summaries.

Treat results as a public, search-indexed sample rather than a complete X export. Search engines and X may omit recent posts, replies, deleted content, protected accounts, engagement counts, or pages blocked from indexing. Never imply exhaustive coverage.

This skill is read-only. Do not publish replies, like posts, follow accounts, send messages, or modify any account.

## Workflow

1. Identify the handle, brand, topic, keywords, date range, language, and desired result count from the request. Ask only when a missing detail would materially change the search; otherwise use a sensible default and state it.
2. Use Glean web search with multiple focused queries. Combine the target with queries such as:
   - `site:x.com \"@HANDLE\"`
   - `site:x.com/status \"BRAND NAME\"`
   - `site:x.com/status \"#HASHTAG\"`
   - `site:x.com/status HANDLE keyword`
   - `site:x.com/status (question OR problem OR love) \"BRAND\"`
3. Apply supported time filters. If exact date filtering is unavailable, add date terms to queries and verify visible timestamps when opening results.
4. Open promising results when possible. Record the canonical X URL, author, visible date, and post text. If only a search-result snippet is accessible, label the item as snippet-derived rather than treating it as a verified full post.
5. Exclude duplicates by canonical post URL or post ID. Exclude the user's own posts when the request asks for posts from other people.
6. Analyze only the evidence found. Classify sentiment as positive, neutral, negative, or unclear; identify repeated questions, complaints, praise, topics, and reasonable opportunities to respond.
7. Cite each post or source beside the finding it supports. State the search window, queries or coverage, number of unique posts found, and the public-indexing limitation.

## Quality rules

- Prefer direct `x.com/<account>/status/<id>` sources over aggregators or copied screenshots.
- Preserve the distinction between verified post content and search snippets.
- Do not invent post text, authors, dates, engagement counts, sentiment, or completeness.
- Do not claim to have searched all of X.
- If results are sparse, say so and suggest a narrower query, a longer date window, or an authenticated/API-based method as an optional upgrade.
- Follow Glean's normal citation format and preserve links to the original X posts whenever available.

## Output

Return:

- A concise overall sentiment and themes summary.
- A table or short list of relevant posts with author, date when available, brief paraphrase, sentiment, verification status, and source citation.
- Recurring questions, complaints, praise, and response opportunities.
- A limitations note explaining that results cover publicly indexed pages rather than the complete X timeline.
