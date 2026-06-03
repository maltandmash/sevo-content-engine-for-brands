# SEvO Content Engine (single brand)

> A multi-agent pipeline that turns a topic into content built to be found and cited across search and AI answer engines, in your brand's voice, with compliance gated in. This is the single-brand edition: set your brand up once and every piece uses it. Built for Claude Code and the Claude desktop app.

Read this first, then `house-style.md`, then `reference/sevo-principles.md`, then your brand's voice pack, before doing anything.

## Where the files live (read this, it stops the engine running blind)

Two separate locations. Do not confuse them.

- **The engine's own files** ship inside the plugin: this `CLAUDE.md`, `house-style.md`, `agents/`, `reference/` and the blank brand templates in `brand/`. When the plugin is installed, resolve every reference to them against the plugin install folder, which is `${CLAUDE_PLUGIN_ROOT}`, for example `${CLAUDE_PLUGIN_ROOT}/agents/02-writer-agent.md`. If you cannot read them, do not improvise the pipeline from memory. Find the plugin folder that holds this CLAUDE.md and the agents/ folder, or tell the user the plugin may not be installed, and stop.
- **Your brand folder** holds your `voice-pack.md`, `approved-facts.md`, `content-status.md` and your `drafts/`. It is your data and lives in your own space, never inside the plugin, because the plugin is replaced on update.

## Your brand folder

This edition serves one brand: yours. The brand folder is the single source. It is one of:

- a folder called `brand/` in your working folder, which is the default, or
- your existing company brand folder, if you point the engine at it during setup. In that case the engine reads your brand material there and keeps `approved-facts.md` and `content-status.md` alongside it.

The plugin ships blank templates at `${CLAUDE_PLUGIN_ROOT}/brand/`. On first setup the engine copies them into your brand folder and fills them in with you. After that, your brand folder is what every job reads and writes.

Mapping note: the shared agent and reference files sometimes say "the working folder" or "SEvO/<brand>/". In this edition that always means your one brand folder.

## Voice resolution, and the first-run voice check

At the start of every job:

1. If the engine has been pointed at a company brand folder, use it.
2. Else use the `brand/` folder in the working folder.
3. If neither is set up, run setup at `${CLAUDE_PLUGIN_ROOT}/commands/voice-pack.md`.

**First-run rule.** If the brand folder has no saved voice pack yet, do not just write. If you can infer the voice from existing brand material, draft a voice pack and confirm the tone of voice with the user in a short step (tone, mention mode, words to avoid, named author), then save it to the brand folder. Otherwise run the setup interview. Never write in a generic or unconfirmed voice.

## The pipeline

Run the agents in order. Each lives at `${CLAUDE_PLUGIN_ROOT}/agents/`. Read the agent file, do its job, pass the output on.

```
1. Research      agents/01-research-agent.md
        |
   [APPROVAL GATE]  show the angle, outline and target surfaces. Wait for a yes.
        |
2. Writer        agents/02-writer-agent.md
3. Fact-check    agents/03-fact-check-agent.md
4. Compliance    agents/04-compliance-agent.md      <-- hard stop if it fails
5. E-E-A-T       agents/05-eeat-agent.md
6. Editor        agents/06-editor-agent.md
7. SEvO polish   agents/07-sevo-agent.md
        |
   [SIGN-OFF GATE]  regulated sectors: route to a qualified reviewer. Never auto-publish.
```

The same stages are also registered as subagents when the plugin is installed. The agent files are the source of truth for each stage.

### The two gates are not optional

- **Approval gate after research.** Show the recommended angle, the outline, the primary query cluster and the target surfaces. Get a yes before writing. For a small job the user can wave it through in one line.
- **Sign-off gate at the end.** For finance, health, insurance or any health or money claim, the draft is not finished copy. It carries `[VERIFY]` flags and a reviewer note. A human signs off before anything goes live.

## What the engine produces

A draft pack in your brand folder under `drafts/<slug>/`, never inside the plugin:

- `article.md` (frontmatter, and a linked Sources section)
- `repurposing-pack.md` (the cross-platform assets)
- `review-notes.md` (fact-check log, `[VERIFY]` flags, compliance report, what to test next)

## Commands

| Command | What it does |
|---------|--------------|
| `/voice-pack` | Set up or update your brand voice. Run once. |
| `/sevo-write` | Run the full pipeline for a topic you name, or the next queued piece. |
| `/sevo-status` | Show your content queue, what is published and what is next. |

## Inheritance, in one line

House style and compliance are fixed. Your voice pack sets tone. SEvO sets structure. If voice and compliance conflict, compliance wins and you flag it.
