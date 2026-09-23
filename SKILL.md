---
name: x-tweet-search-by-query
description: "Monitor publicly indexed X (Twitter) discussion about the Larry H. Miller Company and its portfolio using Glean web search. Find brand mentions, sentiment, questions, complaints, praise, emerging issues, and response opportunities with citations. No Browser Act, X login, API key, cookies, or local scripts required."
---

# Larry H. Miller Company X Social Listening in Glean

Monitor public discussion about the Larry H. Miller Company (LHM) and its portfolio through Glean web search. This is a read-only workflow and requires no Browser Act, logged-in X session, cookies, X API key, or local scripts.

## Business context

LHM is a family investment firm with four primary platforms: Real Estate, Senior Health, Sports + Entertainment, and Investments. Portfolio ownership changes over time, so use current LHM sources in Glean or `lhm.com/portfolio` to confirm the relevant entities before broad monitoring.

Common monitoring targets include:

- Corporate: Larry H. Miller Company, LHM Company, Larry H. Miller, and `lhm.com`.
- Real Estate: Larry H. Miller Real Estate, Daybreak, Downtown Daybreak, The Power District, Destination Homes, TallyCM, and Larry H. Miller Construction.
- Senior Health: Larry H. Miller Senior Health, Advanced Health Care, Advanced Home Health and Hospice, Aspen Ridge, and Advanced Senior Care.
- Sports + Entertainment: Miller Sports + Entertainment, Real Salt Lake, Utah Royals FC, Salt Lake Bees, The Ballpark at America First Square, Megaplex, and Big League Utah.
- Investments: Swig, TaylorMed MRI, and Prestige Financial Services.

Do not assume every reference to “Miller,” “LHM,” “RSL,” “Prestige,” or “Daybreak” concerns the company. Confirm context before including it. LHM dealerships were sold in 2021; treat dealership mentions as legacy or possible brand-confusion signals unless the request specifically includes automotive history.

## Scope and boundaries

Use this skill for brand and reputation monitoring, campaign or event tracking, customer and guest feedback, community reaction, portfolio-company discussion, and emerging-issue detection.

Results are a public, search-indexed sample—not a complete X export. Search engines and X may omit recent posts, replies, deleted content, protected accounts, engagement counts, or pages blocked from indexing. Never imply exhaustive coverage.

This skill is read-only. Do not reply, like, follow, message, or modify any account. Draft response suggestions only when useful, and label them as drafts requiring human review.

## Workflow

1. Determine the requested platform, portfolio company, campaign, event, geography, language, date range, and desired result count. For a company-wide request, search the parent brand and each relevant platform separately.
2. Verify the current portfolio and official brand names using trusted LHM sources in Glean. Use internal company material for context, not as evidence of public sentiment.
3. Run several focused Glean web searches. Use direct brand names, common aliases, handles when known, and queries such as:
   - `site:x.com/status "Larry H. Miller"`
   - `site:x.com/status ("LHM Company" OR "Larry H Miller Company")`
   - `site:x.com/status "BRAND NAME" (Utah OR LOCATION)`
   - `site:x.com/status "BRAND NAME" (question OR problem OR love OR review)`
   - `site:x.com/status "EVENT OR CAMPAIGN"`
4. Apply supported time filters. If exact filtering is unavailable, add date terms and verify visible timestamps on opened results.
5. Open promising results when possible. Record the canonical X URL, author, visible date, referenced LHM entity, and post meaning. Label search-snippet-only items as snippet-derived.
6. Exclude irrelevant namesakes and duplicates. Track cross-portfolio mentions separately when one post concerns multiple LHM entities.
7. Classify sentiment as positive, neutral, negative, or unclear. Tag themes such as customer experience, employee experience, community impact, development, health care, sports performance, venue experience, product or service feedback, leadership, philanthropy, safety, and misinformation.
8. Flag potential high-priority items without overstating them: credible safety or patient-care concerns, legal or regulatory claims, discrimination or harassment allegations, coordinated negative attention, rapidly spreading misinformation, threats, or issues affecting multiple portfolio companies.
9. Cite every public finding. State the search window, entities and queries covered, unique-post count, and public-indexing limitations.

## Output

Return:

- An executive summary of sentiment, notable changes, and the most important themes.
- Results grouped by LHM platform or portfolio company.
- A source table with author, date when available, LHM entity, brief paraphrase, sentiment, priority, verification status, and direct citation.
- Recurring questions, complaints, praise, misinformation, and response opportunities.
- A short “watch next” section for developing issues or follow-up searches.
- A limitations note explaining that coverage reflects publicly indexed pages rather than the complete X timeline.

## Quality rules

- Prefer direct `x.com/<account>/status/<id>` sources over aggregators or screenshots.
- Distinguish verified post content from search snippets and internal LHM context.
- Do not invent authors, text, dates, engagement, sentiment, affiliation, or completeness.
- Do not treat criticism as a crisis solely because it is negative; prioritize using evidence, reach signals when available, credibility, severity, and relevance.
- Follow Glean’s normal citation format and preserve original X links whenever available.
