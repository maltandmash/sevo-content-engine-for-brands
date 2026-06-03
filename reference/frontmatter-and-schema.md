# Frontmatter and schema

## Article frontmatter

Every article carries this block. The SEvO agent fills and checks it.

```yaml
---
title: "Title, 50 to 60 characters, primary query near the start"
description: "Meta description, 150 to 160 characters, answers the query, includes the primary term"
publishedDate: "YYYY-MM-DD"
updatedDate: "YYYY-MM-DD"
author: "Real named author from the voice pack"
reviewer: "Named reviewer for regulated sectors, else blank"
category: "From the voice pack categories"
tags: ["tag1", "tag2", "tag3"]
readingTime: 8
primaryQuery: "the main natural-language question this page answers"
queryCluster: ["related question 1", "related question 2", "related question 3"]
relatedPosts: ["slug-1", "slug-2"]
schema: ["Article", "FAQPage"]
---
```

Note the change from the old engine: `primaryQuery` and `queryCluster` replace single-keyword targeting. SEvO optimises for clusters of natural-language questions, not one keyword. `author` and `reviewer` are real and named, because E-E-A-T and regulated sectors need a real person, not "Editorial Team".

## Schema markup (recommend in review-notes, do not hand-code unless asked)

Pick the types that fit the page. These help machines parse the content and lift citation odds.

| Schema type | Use it when | Key fields |
|-------------|-------------|------------|
| Organization | Every site, once | name, url, logo, sameAs (social and entity profiles) |
| Article | Any article or guide | headline, author, datePublished, dateModified, image |
| FAQPage | The page has a real FAQ section | each question and answer in full |
| HowTo | Step-by-step instructions | each step, tools, time |
| Product | Ecommerce product or reviewed product | name, description, price, availability, aggregateRating |
| Review | First-hand review or test | itemReviewed, author, reviewRating |

Rules:

- Schema must match the visible content. Do not mark up an FAQ that is not on the page.
- Fill all relevant fields. Half-filled schema is a weak signal.
- For Product and Review, ratings and prices must come from `approved-facts.md` or the client feed, never invented.

## Technical notes the SEvO agent always includes in review-notes

- Confirm robots.txt allows GPTBot, OAI-SearchBot, ClaudeBot, PerplexityBot and Google-Extended. Blocked means the page cannot be cited.
- Confirm the answer content is in static HTML, not hidden in accordions, tabs or "read more".
- Confirm HTTPS, a sensible internal link or two to related pages, and that the page is in the sitemap.
- Confirm the article ends with a "## Sources" section and that every external claim is cited inline with a working link. See `reference/sourcing-standard.md`.
