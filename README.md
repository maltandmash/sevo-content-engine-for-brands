# SEvO Content Engine (for brands)

Content for the way people search now: Google, plus AI answer engines (ChatGPT, Gemini, Perplexity, Claude), Reddit, YouTube and the rest. Set up your brand once, then it researches, drafts, fact-checks, compliance-checks and edits in your voice and hands you a draft built to be cited, not just to rank.

This is the single-brand edition, for one company. It runs on your Claude subscription. No API keys. No per-article cost.

## What makes it different

- **It writes in your voice, not a generic one.** You set up a brand voice once. Every piece sounds like you.
- **It will not make things up.** Stats, prices and claims only appear if you have approved them. Everything else is flagged for you to check, with a linked source.
- **It is built for AI search, not just Google.** Answer-first structure, clean chunks, schema, comparison tables and the cross-platform assets that get a brand cited in AI answers.
- **Compliance is built in.** Regulated sectors get gated and flagged for sign-off. It never pretends a draft is finished live copy.

## Setting up

First, the one prerequisite: connect a folder to the Claude desktop app as your workspace. Your brand details and your finished drafts live there. They never live inside the plugin, because the plugin is replaced whenever it updates. Installing the plugin on its own does not write anything.

There are two ways to set up. Both end in the same place: a brand folder in your workspace holding `voice-pack.md`, `approved-facts.md` and `content-status.md`.

### Path 1: your brand pack was prepared for you (recommended)

If your agency or consultant has given you a ready-made brand folder:

1. Connect your content folder in the Claude desktop app.
2. Drop the brand folder inside it.
3. Install the plugin.
4. Ask for a piece, or run `/sevo-write`. The engine finds your brand folder, confirms the voice with you in one line, then writes.

This is the safer route, especially in regulated sectors, because the facts and compliance rules are set by someone who knows them rather than guessed.

### Path 2: set it up yourself

1. Connect a content folder in the Claude desktop app.
2. Install the plugin.
3. Run `/voice-pack`, or just ask for a piece of content and it runs setup first. It asks you a handful of questions in the chat and saves your brand details in a `brand` folder in your workspace. No files to edit by hand.
4. Run `/sevo-write` with a topic.

Either way, on the first piece the engine confirms your tone of voice before it writes, then remembers it. Order does not matter much: you can install the plugin before or after the brand folder exists, because the engine reads the brand folder fresh each time it runs.

## Commands

| Command | What it does |
|---------|--------------|
| `/voice-pack` | Set up or update your brand voice. Run once. |
| `/sevo-write` | Research and draft a piece, through the full pipeline. |
| `/sevo-status` | See your content queue and what is published. |

## How it works

Seven stages, each a focused agent, run in order: research, write, fact-check, compliance, E-E-A-T, edit for voice, SEvO polish. You approve the angle after research, then it produces a draft pack: the main article, a cross-platform repurposing pack and a review-notes file with everything flagged for checking. For regulated sectors it stops for a human to sign off.

## What is in this repo

Two kinds of thing live here: the engine (shipped with the plugin, you do not edit it) and the brand templates (copied into your own folder, which you do edit). Your real brand files and finished drafts live in your workspace, never inside the plugin, because the plugin is replaced on update.

```
sevo-content-engine-for-brands/
├── .claude-plugin/
│   └── plugin.json            Plugin manifest: name, version, description
├── README.md                  This file
├── LICENSE
├── CLAUDE.md                  The orchestrator: how the pipeline runs, the two gates, where files live
├── house-style.md             The non-negotiables: accuracy, compliance, British English defaults
├── agents/                    The seven pipeline stages, run in order
│   ├── 01-research-agent.md
│   ├── 02-writer-agent.md
│   ├── 03-fact-check-agent.md
│   ├── 04-compliance-agent.md
│   ├── 05-eeat-agent.md
│   ├── 06-editor-agent.md
│   └── 07-sevo-agent.md
├── reference/                 Shared knowledge the agents read
│   ├── sevo-principles.md
│   ├── compliance-map.md
│   ├── frontmatter-and-schema.md
│   ├── repurposing-pack.md
│   └── sourcing-standard.md
├── commands/                  The slash commands
│   ├── voice-pack.md
│   ├── sevo-write.md
│   └── sevo-status.md
├── skills/
│   └── sevo-content/
│       └── SKILL.md           Natural-language trigger for the whole engine
├── brand/                     Blank brand templates, copied into your brand folder on setup
│   ├── voice-pack.md
│   ├── approved-facts.md
│   └── content-status.md
└── drafts/
    └── README.md              Placeholder; real drafts save to your brand folder
```

### The engine (shipped, do not edit)

- **`CLAUDE.md`** is the brain. It sets the run order, the approval gate after research, the compliance hard stop, the final sign-off gate, and the rule that the engine reads its own files from the plugin folder and your brand files from your workspace.
- **`house-style.md`** holds the rules nothing can override: never invent facts, link every source, compliance wins over voice, British English by default. Your voice pack can change tone but not these.
- **`agents/`** is the pipeline, one file per stage:
  - `01-research-agent` finds the query cluster, the surfaces that matter, the sources and the angle, then stops for your approval.
  - `02-writer-agent` drafts answer-first and chunk-friendly, in your voice, using only approved facts.
  - `03-fact-check-agent` checks every claim and flags anything unproven with `[VERIFY]`.
  - `04-compliance-agent` is a hard gate: it checks the draft against the sector rules and flags regulated content for sign-off.
  - `05-eeat-agent` adds real experience, expertise and trust signals, never invented ones.
  - `06-editor-agent` edits for your voice and readability.
  - `07-sevo-agent` applies the SEvO structure and schema, then builds the repurposing pack and writes the draft pack.
- **`reference/`** is the shared knowledge every stage draws on:
  - `sevo-principles.md`, the Search Everywhere thinking: answer-first, chunk-friendly, query clusters, be the source AI cites.
  - `compliance-map.md`, sector to regulators to hard rules (ASAI, Central Bank of Ireland, HIA, Charities Regulator and more).
  - `frontmatter-and-schema.md`, the article frontmatter and the schema types to use.
  - `repurposing-pack.md`, how to turn one article into Reddit, LinkedIn, YouTube and social assets.
  - `sourcing-standard.md`, the rule that every source is linked and every article ends with a Sources section.
- **`commands/`** are the three slash commands, written as instructions for Claude: `voice-pack` (the guided setup interview), `sevo-write` (run the pipeline) and `sevo-status` (show the queue).
- **`skills/sevo-content/SKILL.md`** is the natural-language trigger, so asking for a blog post or article starts the engine without needing a command.

### Your brand and your output (yours to edit)

- **`brand/`** holds blank templates only. On setup the engine copies them into your brand folder (a `brand/` folder in your workspace, or your company brand folder) and fills them in with you:
  - `voice-pack.md`, your tone, audience, mention mode, words to avoid and named author.
  - `approved-facts.md`, the only place the engine takes stats, prices and claims from.
  - `content-status.md`, your queue, what is published and your topic clusters.
- **`drafts/`** is a placeholder. Real draft packs are written to your brand folder under `drafts/<slug>/`, each one an `article.md`, a `repurposing-pack.md` and a `review-notes.md`.

## One brand or many?

This is the single-brand edition. If you run content for several brands or clients, use the agency edition, which keeps a separate voice pack per client under one install.

## What it does not do

- Images and video. Use your normal tools. The repurposing pack gives you the briefs.
- Publishing. It writes the draft. You or your reviewer publish it.
- Live AI-visibility tracking. It tells you what to measure, not your live numbers.
