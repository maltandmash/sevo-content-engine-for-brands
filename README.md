# SEvO Content Engine

Content for the way people search now: Google, plus AI answer engines (ChatGPT, Gemini, Perplexity, Claude), Reddit, YouTube and the rest. Set up your brand once, then it researches, drafts, fact-checks, compliance-checks and edits in your voice and hands you a draft built to be cited, not just to rank.

It runs on your Claude subscription. No API keys. No per-article cost.

## What makes it different

- **It writes in your voice, not a generic one.** You set up a brand voice once. Every piece sounds like you.
- **It will not make things up.** Stats, prices and claims only appear if you have approved them. Everything else is flagged for you to check, with a linked source.
- **It is built for AI search, not just Google.** Answer-first structure, clean chunks, schema, comparison tables and the cross-platform assets that get a brand cited in AI answers.
- **Compliance is built in.** Regulated sectors get gated and flagged for sign-off. It never pretends a draft is finished live copy.

## Setup (about 5 minutes)

1. **Install the plugin** in the Claude desktop app or Claude Code.
2. **Set up your brand.** Run `/voice-pack`, or just ask for a piece of content and it runs setup first. It asks a handful of questions in the chat and saves your brand details in a `brand` folder in your workspace. If your company already keeps a brand folder, you can point it there instead. No files to edit by hand.
3. **Write.** Run `/sevo-write` with a topic, or let it take the next one from your queue.

Your brand details and drafts live in your own folder, never inside the plugin, so they survive updates. On the first piece the engine confirms your tone of voice before it writes, then remembers it.

## How it works

Seven steps, each a focused agent: research, write, fact-check, compliance, E-E-A-T, edit for voice, SEvO polish. You approve the angle after research, then it produces a draft pack: the main article, a cross-platform repurposing pack and a review-notes file with everything flagged for checking.

Read `CLAUDE.md` for the full pipeline and `reference/sevo-principles.md` for the thinking behind it.

## Commands

| Command | What it does |
|---------|--------------|
| `/voice-pack` | Set up or update your brand voice |
| `/sevo-write` | Research and draft a piece |
| `/sevo-status` | See your content queue |

## One brand or many?

This is the single-brand edition, for one company. If you run content for several brands or clients, use the agency edition, which keeps a separate voice pack per client under one install.

## What it does not do

- Images and video. Use your normal tools. The repurposing pack gives you the briefs.
- Publishing. It writes the draft. You or your reviewer publish it.
- Live AI-visibility tracking. It tells you what to measure, not your live numbers.
