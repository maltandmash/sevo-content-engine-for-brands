---
description: Research and draft a piece of SEvO content through the full pipeline
argument-hint: "[topic, optional]"
allowed-tools: AskUserQuestion, Read, Write, Edit, Glob, Grep, WebSearch, WebFetch
---

The user wants to write a piece. Topic if given: $ARGUMENTS

1. **Find the engine files first.** Read `${CLAUDE_PLUGIN_ROOT}/CLAUDE.md`, `${CLAUDE_PLUGIN_ROOT}/house-style.md`, `${CLAUDE_PLUGIN_ROOT}/reference/sevo-principles.md` and `${CLAUDE_PLUGIN_ROOT}/reference/sourcing-standard.md`. If you cannot read them, find the plugin folder that holds them or tell the user the plugin may not be installed, and stop. Do not improvise the pipeline from memory.

2. **Find the brand and confirm the voice.** The brand folder is the single source: a `brand/` folder in the working folder, or the company brand folder the user has pointed the engine at. First-run rule: if there is no saved voice pack, set one up before writing. If you can infer the voice from existing brand material, draft a voice pack and confirm the tone of voice in a short step (tone, mention mode, words to avoid, named author), then save it to the brand folder. Otherwise run the setup in `${CLAUDE_PLUGIN_ROOT}/commands/voice-pack.md`. Never write in an unconfirmed voice.

3. **Pick the topic.** If a topic is given, use it. If not, read the brand's `content-status.md` and take the next queued item. Confirm in one line.

4. **Run the pipeline** from `${CLAUDE_PLUGIN_ROOT}/agents/`, in order: research, then stop at the approval gate and show the angle, query cluster, target surfaces and outline. Wait for a yes. Then writer, fact-check, compliance (hard stop if it fails), E-E-A-T, editor, SEvO polish.

5. **Write the draft pack** to the brand folder under `drafts/<slug>/`, never inside the plugin: `article.md`, `repurposing-pack.md`, `review-notes.md`.

6. **Report back** in one short message: where the draft pack is, the headline `[VERIFY]` flags, the compliance decision and whether a qualified reviewer is needed, and a one-line "What I'd do next". For regulated sectors, state plainly that this is a draft for sign-off, not finished copy.

Self-check before handing over: useful today, next step obvious, anything that would make a regulator, lawyer or customer uneasy. If yes to the last one, stop and flag.
