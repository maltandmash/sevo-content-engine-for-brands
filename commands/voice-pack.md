---
description: Set up your brand voice in a few questions (start here)
argument-hint: "[brand name, optional]"
allowed-tools: AskUserQuestion, Read, Write, Edit, Glob, Grep, WebFetch
---

Set up the brand's voice pack by interviewing the user in the chat, one step at a time, then save it to their brand folder. Brand name if given: $ARGUMENTS

## How to run this

- Keep every message short and plain. Do not show file paths, folder names or schema field names. The user answers questions, you do the filing.
- Use the question chooser (AskUserQuestion) for any step that has a fixed set of answers, and batch related choices into one chooser call, up to four at a time. Use normal chat for open answers like names, phrases and facts.
- The chooser always gives a skip option and a free-text box, so offer the common options and let them type their own.
- If they skip something, record it as still needed and move on. Never invent an answer.

## Where the brand details are saved

The brand folder is the single source and lives in the user's own space, never inside the plugin. Copy the blank templates from `${CLAUDE_PLUGIN_ROOT}/brand/` into it and fill them in.

## The steps, in order

1. **Welcome and where to keep it.** One short message: you will ask a handful of questions to capture their voice, the facts they are happy to publish and, if they want, their first topic. Then ask with the chooser: "Where should I keep your brand details?" Options: "A new brand folder here", "My existing company brand folder" (then get the path in chat). Then ask "How should I learn your brand voice?" Options: "From my brand guidelines", "Learn from a few links of my content", "Just ask me questions". For the links route, get three to five URLs and read them with WebFetch, then show your draft and ask them to correct it. If brand material already exists in the company folder, offer to draft from it and have them confirm.

2. **The basics** (open chat). Brand name (use $ARGUMENTS if given), what they sell in a line, who they sell to, and their website.

3. **Market and reading level** (chooser, batch): Region and language (Ireland British English, UK British English, US US English, Other); Reading level (Plain age 12 to 14, Mid 14 to 16, Professional); Sector (offer the four most likely, let them type if not listed: charity, FMCG, healthcare, investment or finance, B2B, publishing, ecommerce).

4. **How the brand shows up** (chooser): "Lead with the product", "Mention the service naturally", "No selling, useful content only". Explain each in a few words.

5. **Tone** (chooser, multi-select, then chat). "Pick the words that fit your voice", offer four that suit the sector plus the free-text box. Then in chat ask for phrases they use word for word, and any words to ban.

6. **Formatting** (chooser, batch): Oxford comma (No, Yes); Emoji (Never, Sparingly, Freely); Headlines (Sentence case, Title case). English variant follows the region. Default to no em dashes and straight quotes unless they say otherwise.

7. **Author** (open chat). Who is named as the author and one line on why they are credible. For regulated sectors, who signs content off.

8. **Facts they can publish** (open chat). Any stats, prices, ratings or claims they are happy to stand behind, each with the figure and date. This is the only place facts come from. Anything not listed is flagged for checking, not guessed.

9. **Compliance** (from sector). Tell them plainly which rules apply, using `${CLAUDE_PLUGIN_ROOT}/reference/compliance-map.md`. For finance, health or insurance, say drafts will be held for a qualified person to sign off, and confirm who that is.

10. **First topic** (chooser): "Want to line up your first piece now?" Yes (ask the topic in chat) or Not yet.

11. **Save and confirm.** Create the brand's `voice-pack.md`, `approved-facts.md` and `content-status.md` in the brand folder chosen in step 1, based on the templates at `${CLAUDE_PLUGIN_ROOT}/brand/`, never inside the plugin. Mark anything skipped as still needed. Show a short plain summary: the voice in two lines, how the brand shows up, the sector and rules, how many approved facts you captured, and anything outstanding. End with a one-line "What I'd do next".

## Updating later

If a voice pack already exists in the brand folder, read it, say what is set, and ask only what they want to change.
