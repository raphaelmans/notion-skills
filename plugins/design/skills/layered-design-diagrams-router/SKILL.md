---
name: |-
  layered-design-diagrams-router
description: |-
  Entry point for diagramming a feature or PRD module in layers: state machine → design-pattern flowchart → inside-a-module sequences. Reads the request, picks which level(s) to produce, and loads only those level skills. Use for 'full-blown diagrams', 'just the flowchart', 'show me the sequence for X', 'state machine for Y'. Not for ERDs, UI mockups or slide decks.
notion_page_id: 4149439f-1486-81ca-9415-d6043a915f51
---

## When to use

Use this when I want to understand or design a feature or PRD module through diagrams. This page is the interface. It routes to three level skills and loads only the ones the request needs.

Not for: database schemas (ERDs), UI mockups, slide decks, or a single quick sketch in chat.

## The three levels

Each level answers a different question using the diagram type best suited to it. Never draw the same story twice in two diagram types.

| Level | Question it answers | Diagram | Skill |
| --- | --- | --- | --- |
| 1 | What states does the main thing go through? | State machine | <mention url="https://app.notion.com/p/4149439f148681fa97e3e7d7d51ba97c">Layered diagrams 1 · Lifecycle state machine</mention> |
| 2 | How is the design shaped? Where are the patterns and runtime choices? | Flowchart | <mention url="https://app.notion.com/p/4149439f1486818a8dd8ccfe031e4668">Layered diagrams 2 · Design-pattern flowchart</mention> |
| 3 | Inside one module, how do its parts work together? | Sequence | <mention url="https://app.notion.com/p/4149439f148681c0970ed2e72ecbca08">Layered diagrams 3 · Inside-a-module sequence</mention> |

## Step 1 · Route the request

Match the request to one row, then load only the skills in that row.

| If the request says… | Produce | Load |
| --- | --- | --- |
| "full", "full-blown", "all levels", "deep dive", "walk me through the whole module" | Levels 1 → 2 → 3 | All three, in order |
| "state machine", "lifecycle", "what states", "statuses" | Level 1 only | Level 1 |
| "flowchart", "architecture", "patterns", "hexagonal", "strategy", "adapter", "how it's shaped" | Level 2 only | Level 2 |
| "sequence", "inside \<module>", "how does \<module> work", "I want to learn \<module>" | Level 3, for the named module(s) | Level 3 |
| Two levels named, e.g. "flowchart and sequences" | Those levels, in level order | Those skills |
| Just "diagram \<feature>", with nothing else | Ask one question with 4 options: Full, State machine, Patterns flowchart, Module sequence | Nothing until answered |

If Level 3 is asked for without a module name and there is no Level 2 to take one from, name 3 or 4 likely modules and ask which.

## Step 2 · Gather the inputs

- **Subject (required):** the feature or PRD module. If it lives in Notion, fetch the PRD page first and use its rules. If there is no subject, ask once.
- **Project layering:** default is Router → UseCase → Service → Repository, with vendors behind adapters. Use the project's own layering if the PRD or repo states it.
- **Worked example:** invent ONE concrete scenario and use it in every level. Give it a named person, a real item, real numbers in the right currency, and real vendors from the stack. Example: "Maria books Court 2, Sat 6–7pm, ₱500 base, pays with GCash via PayMongo." Mark anything invented as an example, not as a fact from the PRD.
- **Unknown rules:** never guess. Put them under Open questions with ⚑.

## Step 3 · Rules that apply to every level

- Plain behavioural language first, with pattern names second, in brackets or band titles. Write "Money port", not "IPaymentGateway".
- No class or method names in diagrams. A short collapsed code sketch is allowed at Level 2 only.
- Mermaid only, one caption sentence per diagram explaining how to read it.
- Each level zooms into part of the level above. Level 1 highlights the path that Level 2 opens up. Level 2 lists the modules that Level 3 opens up.
- Keep diagrams within budget: about 10 states, 5 bands, and 16 messages.

## Step 4 · Output

Default: one reviewable HTML artifact page (a Claude artifact) titled "\<Feature> design", with these sections in order:

1. Header: a one-sentence summary, plus zoom pills reading "Level 1 · … / Level 2 · … / Level 3 · …" for the levels produced.
2. One card per diagram, each with a kicker (e.g. "Level 2 · Flowchart · Design patterns"), a heading, a caption and the diagram. Use `<pre class="mermaid">`, since artifacts render Mermaid natively.
3. A key that maps each plain word to its pattern name. For example: Way in → driving adapter, Plug → port, Provider behind a plug → adapter, Swappable rule → strategy.
4. Open questions marked ⚑, if any.

Follow-up requests ("add Level 3 for payments", "just redo the flowchart") update the SAME artifact instead of creating a new one.

Fallbacks:

- No artifact tool → a Notion page using the "Write a design doc page with diagrams" outline, with the same diagrams.
- No Notion either → Mermaid blocks in chat.

## Done when

- [ ] Only the requested levels were produced, and only their skills were loaded.
- [ ] The same worked example runs through every level.
- [ ] No two diagrams tell the same story.
- [ ] The output link is returned with one line per level produced.

## Reference

The first finished example is the "Booking modules" Claude artifact (court booking, PayMongo and Stripe adapters, pricing strategies), built 2026-11-10.
