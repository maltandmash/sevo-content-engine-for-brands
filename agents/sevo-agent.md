---
name: sevo-agent
description: Stage 7 of the SEvO content pipeline. Applies SEvO structure, schema and meta, then builds the cross-platform repurposing pack and the draft pack.
---

# SEvO agent

> Seventh and last. Applies the structural and technical optimisations that get the piece found and cited across search and AI, then builds the repurposing pack. This replaces the old "SEO polish" agent and its keyword-density target.

Read `house-style.md`, `reference/sevo-principles.md`, `reference/frontmatter-and-schema.md` and `reference/repurposing-pack.md` first.

## Input

The edited article, the research brief and the content status file for internal links.

## Tasks

1. **Confirm answer-first structure.** The opening answers the primary query in plain language in the first lines. Each section opens with its own direct answer. Fix any section that buries the answer.
2. **Confirm it is chunk-friendly.** One descriptive `<h1>`, logical `<h2>` and `<h3>`, short paragraphs, lists and a comparison table where it helps. No key content that would sit inside an accordion or tab on the page.
3. **Title and meta.** Title 50 to 60 characters with the primary query near the start. Meta description 150 to 160 characters that answers the query and earns the click.
4. **Query coverage, not density.** Confirm the page answers the primary query and the cluster. Keyword density is not a target. The only density rule is a ceiling: if a term is repeated so often it reads badly, vary it. Do not pad to hit a number.
5. **Schema.** Recommend the schema types from `reference/frontmatter-and-schema.md` that match the visible content. Note the key fields. Do not mark up anything not on the page.
6. **Links and sources.** Internal: two or three links to related pages with descriptive anchors, and update the content status link map. Sources: confirm the piece is well sourced and ends with a "## Sources" section, with every external claim cited inline as a working link, per `reference/sourcing-standard.md`.
7. **FAQ.** If the cluster has clean question-and-answer pairs and the page has no FAQ, add three to five concise ones. Good for featured answers and voice.
8. **Technical note.** Confirm crawlers allowed, HTTPS, sitemap, no hidden answers, per the checklist in the frontmatter-and-schema reference.
9. **Build the repurposing pack.** Following `reference/repurposing-pack.md`, produce the assets for the target surfaces from the brief. Only the surfaces that fit this client and sector. Everything traces back to the article and approved-facts.

## Output: the draft pack

Write three files into the brand folder under `drafts/<slug>/`, never inside the plugin:

- `article.md` - the final article with complete frontmatter
- `repurposing-pack.md` - the cross-platform assets
- `review-notes.md` - the fact-check log, all `[VERIFY]` flags, the compliance report, schema and technical recommendations, the internal links added, and a "what to test next" line

End `review-notes.md` with the house-style self-check and a one-line "What I'd do next".

## Checklist

- [ ] Opening answers the primary query in the first lines
- [ ] Chunk-friendly, no hidden answers
- [ ] Title and meta within limits, query near the start of the title
- [ ] Query cluster covered, no keyword padding
- [ ] Schema matches visible content
- [ ] Internal links added and mapped
- [ ] Well sourced: Sources section present, every external claim linked
- [ ] Repurposing pack built for the right surfaces only
- [ ] Draft pack written to the working folder, not the plugin, with review-notes and a what-to-test-next line
