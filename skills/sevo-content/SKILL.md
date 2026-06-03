---
name: sevo-content
description: "Use this skill whenever the user wants to write, plan or refresh organic content built to rank and to be cited by AI answer engines: blog articles, pillar pages, comparison or how-to guides, FAQ pages, or a cross-platform content pack. Runs a seven-stage pipeline (research, write, fact-check, compliance, E-E-A-T, edit, SEvO polish) in the brand's voice, takes facts only from an approved-facts file, gates regulated sectors for sign-off, and outputs a draft article plus a repurposing pack for Reddit, LinkedIn, YouTube and social. Do not use for paid ad copy or for pure technical SEO audits."
---

# SEvO Content Engine (single brand)

## When to use

Trigger when the user says any of:

- "Write a blog post / article / guide about [topic]"
- "Write a pillar page / comparison / how-to"
- "Refresh this article for AI search"
- "Make content that gets cited by ChatGPT / Google AI"
- "Build a content pack around [topic]"

Do not use for paid ad copy or a standalone technical SEO crawl.

If the brand is not set up yet, or the user says "set up my brand", "get started" or "onboard", run the setup interview in `${CLAUDE_PLUGIN_ROOT}/commands/voice-pack.md` first, then continue. This is how a brand gets onboarded without needing to know any commands.

## Step 1: find the engine files (do not skip)

The engine's machinery ships with this plugin under `${CLAUDE_PLUGIN_ROOT}`: `CLAUDE.md`, `house-style.md`, `reference/` and `agents/`. Read `${CLAUDE_PLUGIN_ROOT}/CLAUDE.md` first, then `house-style.md`, `reference/sevo-principles.md` and `reference/sourcing-standard.md`.

If you cannot read these files, do not run the pipeline from memory. Find the plugin folder that holds this skill and the agents/ folder, or tell the user the plugin may not be installed correctly and stop.

## Step 2: find the brand, and confirm the voice on the first run

The brand folder is the single source: a `brand/` folder in the working folder, or the company brand folder the user has pointed the engine at. See CLAUDE.md.

First-run rule: if the brand has no saved voice pack, do not write yet.

- If you can infer the voice from existing brand material, draft a voice pack, confirm the tone of voice with the user in a short step (tone, mention mode, words to avoid, named author), then save it to the brand folder.
- Otherwise run the setup interview at `${CLAUDE_PLUGIN_ROOT}/commands/voice-pack.md`.

Never write in a generic or unconfirmed voice.

## Step 3: run the pipeline

Read each agent file in `${CLAUDE_PLUGIN_ROOT}/agents/` and run it in order: research, then the approval gate, then writer, fact-check, compliance (hard stop), E-E-A-T, editor, SEvO polish. The compliance and sign-off gates are not optional. See CLAUDE.md.

## Output

A draft pack in the brand folder under `drafts/<slug>/`, never inside the plugin: `article.md` (with a linked Sources section), `repurposing-pack.md`, `review-notes.md` with every `[VERIFY]` flag, the compliance report and a "what to test next" line.

## Self-check before handing over

1. Is this useful today?
2. Is the next step obvious?
3. Is anything in here that would make a regulator, lawyer or customer uneasy? If yes, stop and flag.

End with a one-line "What I'd do next".
