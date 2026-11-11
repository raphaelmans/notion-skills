---
name: |-
  mark-brainstorm-artifacts-stale-and-drop-them-from-context
description: |-
  Use when brainstorming artifacts, pages or docs (Claude artifacts, Claude Docs, Notion pages, HTML or Markdown files) have been overtaken by the codebase or a living doc. Rescues any durable decisions, labels the artifacts stale, and removes them from agent context, memory and project links instead of keeping them updated. Not for living docs (PRD, module specs, ADRs, Glossary), which get updated, not staled.
notion_page_id: 4139439f-1486-81ba-8653-f527d73c090e
---

## When to use

Brainstorming produces many artifacts: explainer pages, proposals, diagrams, design drafts, review docs. Once the real decision lands in the source of truth (the codebase, or a living doc such as the PRD or a module spec), these become snapshots. Keeping them updated wastes effort, and leaving them in context misleads agents. This skill freezes them: rescue what matters, label them stale, and cut them out of every place an agent might read them.

**Don't use for** living docs: the parent PRD, module specs, ADRs, the Glossary, repo docs (README, ARCHITECTURE, CONTEXT). When those drift, update them instead.

## Inputs

- **Which artifacts:** links, titles or file paths. If the user says "everything from this brainstorm", list candidates from the conversation, the project's Notion page and recent artifacts, and confirm the list before acting.
- **Source of truth:** where the current truth lives (repo and path, or the living doc). If missing, ask once; if still unknown, write "the codebase".
- **Project:** which Projects page the artifacts belong to, if any.

## Steps

1. **List and classify.** For each artifact, decide one of:
   - **Stale:** a brainstorming snapshot that the source of truth has overtaken.
   - **Promote first:** contains a decision, rule, term or open question that isn't in the source of truth yet.
   - **Keep:** actually a living doc. Leave it alone and say why.<br />Show the list to the user before changing anything.
2. **Rescue durable content (Promote first).** Extract only what still matters, and hand it to its home instead of copying the whole artifact:
   - Decisions → an ADR or the module spec's Decisions.
   - Requirements → the PRD or module spec (via a change doc if the module has one).
   - Terms → the Glossary keeper.
   - Unresolved questions → the project's open items, marked ⚑.<br />Use the handoff format in Agent protocol. Then treat the artifact as Stale.
3. **Label it stale, where it lives.** Put a banner at the very top, without editing the rest:<br />`⚠️ Stale · brainstorming snapshot from [date]. Not maintained. Source of truth: [link or repo path]. Agents: don't use as context.`
   - **Notion page:** the banner as a red callout, and prefix the title with "\[Stale\] ". If it's a database row with a Status property, set it to the closest "archived" option.
   - **Claude Doc:** insert the banner as the first block.
   - **Claude artifact (HTML page):** add the banner to the top of the page and republish to the same link. If you can't edit it, record it in the stale list (step 5) instead.
   - **Local or repo file:** add `status: stale` and `superseded_by:` to its frontmatter, or the banner as the first line, or move it into an `archive/` folder. Never move or delete files the code depends on.
4. **Remove it from context.** Wherever an agent might pick it up:
   - **Project and agent instructions** ([CLAUDE.md](http://CLAUDE.md), [AGENTS.md](http://AGENTS.md), Notion project pages, agent persona pages): remove links that point agents to the artifact, and point to the source of truth instead.
   - **Persistent memory:** remove lines that summarise or link the artifact's content as if it were current. Only do this when the user asked this skill to run; report each removed line.
   - **This chat session:** state plainly which artifacts are now stale and that their content won't be used again. If the session is long and heavily based on them, suggest starting a fresh session with a short handoff that names only the source of truth.
   - **Notion links:** move remaining links on project pages under a collapsed "Stale artifacts" toggle, not in reading order.
5. **Record it.** On the project's Notion page, add each artifact to a "Stale artifacts" toggle: title · link · date · why stale · source of truth. Create the toggle if missing.

## Output

A reply to the user with one table:

| Artifact | Decision (Stale / Promoted then stale / Kept) | What was rescued, and where | Removed from |
| --- | --- | --- | --- |

Then every ⚑ item, and the link to the project's stale list.

## Rules

- Never delete an artifact unless the user explicitly asks. Stale means frozen and labelled, not gone.
- Never update a stale artifact's content to make it current. If it needs to be current, it's a living doc: update the source of truth instead.
- Change only the banner, title prefix and status. Leave the body untouched, so the snapshot stays honest.
- Confirm the classification list (step 1) before making changes.
- Pages or artifacts owned by someone else: only comment with the stale notice; don't edit.
- Don't stale anything that is still the only record of a decision. Rescue first (step 2).
- Keep the Second Brain generic: project-specific stale lists live on the project's page, not in the Second Brain.

## Done checklist

- [ ] Every artifact in scope is classified, and the user confirmed the list.
- [ ] Every durable decision, term or question was handed to its home, or listed as ⚑.
- [ ] Every stale artifact shows the banner (or is in the stale list if it couldn't be edited).
- [ ] No instruction file, memory line or project page still points agents at a stale artifact as current.
- [ ] The project's "Stale artifacts" list is updated.
- [ ] Report sent: the table, links, and every ⚑ item.

## Handoff

- Decisions and requirements → Project manager (module spec, change doc, ADR).
- Terms → Glossary keeper.
- Reusable lessons from the brainstorm → Second Brain operator, as a generic note.
