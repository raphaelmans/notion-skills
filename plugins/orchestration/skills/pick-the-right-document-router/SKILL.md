---
name: |-
  pick-the-right-document-router
description: |-
  Entry point for any 'write up / document / spec / render a doc' request. Reads the ask, picks the matching Playbooks template, decides where it lives, and calls the layered diagram skill only for the levels that doc needs. Use instead of invoking layered diagrams directly when the output is a document. Not for a pure diagram request, quick chat answers, or Second Brain core notes.
notion_page_id: 4169439f-1486-8186-a8d0-fd13cdec6625
---

## When to use

Use when I ask for a document of any kind: "write this up", "spec this", "document X", "render a doc for…". This page is the interface. It picks ONE template, then loads only what that template needs.

Not for:

- A pure diagram ask ("diagram X", "state machine for Y") → go straight to <mention url="https://app.notion.com/p/4149439f148681ca9415d6043a915f51" />.
- A single idea to remember → Second Brain core note, owned by the Second Brain operator.
- A quick answer I'll read once → stay in chat.

## Step 1 · Route the request

Match the question I'm really asking to one row. Phase follows <mention url="https://app.notion.com/p/4119439f148681bab670e63970c76ead" />.

| If I'm asking… | Template | Phase | Diagrams (layered levels) |
| --- | --- | --- | --- |
| "Is this worth building? What's the problem?" | <mention url="https://app.notion.com/p/4119439f148681608209dfc9c19a7a3a" /> | Discover | None |
| "What did users / competitors say?" | <mention url="https://app.notion.com/p/4119439f14868160b2b7c7befc4d5626" /> | Discover | None |
| "Start a brand-new product from scratch" | <mention url="https://app.notion.com/p/4119439f148681bb8440d6ba446b62ee" /> | Discover → Define | None |
| "What are we building, for whom, what's in scope?" | <mention url="https://app.notion.com/p/4119439f14868150a2b3e98a203030fd" /> | Define | None (module map as a list) |
| "How does a user move through it? Journey, flow, onboarding" | <mention url="https://app.notion.com/p/4119439f1486811db821c8afb14e520a" /> | Define | ⚑ No layered level fits user flows yet; use one plain Mermaid flowchart of the steps |
| "One new feature or one change to an existing module" | <mention url="https://app.notion.com/p/4119439f148681ca92a5d72dedbe5f33" /> | Define | Only the level the change touches |
| "What's the shape of the solution? Boundaries, lifecycles" | <mention url="https://app.notion.com/p/4119439f148681c59a2ac66541c3052d" /> | Design | Levels 1 + 2 |
| "Deep dive on one module" (forward or as-built from code) | <mention url="https://app.notion.com/p/4119439f148681688dffe0d334901c80" /> | Design | Levels 1 + 2 + 3 (full) |
| "Exactly how will it be built? Data model, interfaces, rollout" | <mention url="https://app.notion.com/p/4119439f14868126a8ffc1950f225dcc" /> | Design | Levels 1 + 3 |
| "Why did we choose X over Y?" | <mention url="https://app.notion.com/p/4119439f148681639d39f004948d6624" /> | Design | None |
| "How does this platform work?" (explain an existing tool) | <mention url="https://app.notion.com/p/40e9439f148681819d4dd78e873cf615" /> | Any | Level 2 only, if it helps |
| "Something broke, how do I fix it?" | <mention url="https://app.notion.com/p/4149439f148681768d61f90f6e116aca" /> | Launch and run | Level 2 only (how parts connect) |
| A design idea not proven yet | <mention url="https://app.notion.com/p/4129439f148681c9a7d1fa9c0d575803" /> (skill) | Design | As that skill says |

If two rows fit, ask ONE question with the two doc names and a one-line "pick this if…" for each. Don't guess.

If nothing fits, say so, use the nearest template, and log ⚑ "New doc type?" in the Improvement backlog.

## Step 2 · Decide where it lives

- About a specific project → that project's page in Projects.
- A design that isn't built or proven yet → Blueprints, as Draft.
- Generic, reusable knowledge → not a doc; hand off to the Second Brain operator as core notes.
- If I named a place, use it.

## Step 3 · Build it

1. Fetch the chosen template and keep its sections and order. Drop a section only if it's truly empty, and say which.
2. Fill it in plain product language first, technical detail after.
3. For diagrams, load <mention url="https://app.notion.com/p/4149439f148681ca9415d6043a915f51" /> with ONLY the levels from the table, and use one worked example across the whole doc.
4. Unknown facts go under Open questions with ⚑. Never guess.

## Output

One Notion page from the chosen template, in the place from Step 2. Reply with: the doc type and why (one line), the link, and every ⚑ item.

## Rules

- One request, one doc. If I'm really asking for two (e.g. PRD + tech spec), say so and build the earlier phase first.
- Never invoke the layered skill at full depth by habit; the table decides the levels.
- Don't edit the templates themselves; suggest changes in the Improvement backlog.

## Done checklist

- [ ] The template choice is stated with a one-line reason.
- [ ] Only the diagram levels in the table were produced.
- [ ] The page sits in the right place and links back to its project or Blueprint.
- [ ] Report back: doc type, link, ⚑ items.

## Handoff

Project docs → Project manager. Blueprints → stays with the Chief of staff until I promote it. Generic learnings → Second Brain operator.
