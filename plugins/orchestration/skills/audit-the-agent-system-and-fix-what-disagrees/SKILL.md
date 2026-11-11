---
name: |-
  audit-the-agent-system-and-fix-what-disagrees
description: |-
  Use when I say "audit" or "review the agents", or after a structural change (a new agent, skill or layer, or a moved page). Checks that personas, the Agent protocol, the Skills library and the routing table agree with each other, fixes small things, and proposes the rest. Not for auditing one project's content or the Second Brain's notes.
notion_page_id: 4149439f-1486-8109-9033-c44231f6d769
---

## When to use

In Thorough mode, when I ask for an audit, or right after something structural changed. Most problems are pages disagreeing with each other after a change.

## Inputs

- Scope: the whole system by default, or the one thing that changed.

## Steps

1. Read: the Agents page, the Agent protocol, every persona page under Agents, the Agent Skills page with every Skills row (Status, Used by, Description), and the chief of staff's routing table and Improvement backlog.
2. Check that they agree:
   - **Agents:** every agent in the hierarchy has a persona page, a row in the protocol's ownership table and at least one routing row. And the reverse.
   - **Ownership:** each layer has exactly one owner. No two personas claim the same thing.
   - **Handoffs:** they mirror. If one persona "sends to" a role, that role "receives from" it.
   - **Skills:** every skill listed on a persona exists and isn't Retired. Every skill's Used by matches the personas that list it.
   - **Places:** every page or database a persona names still exists where it says.
   - **Persona vs skill:** apply the test on the Agent Skills page. Flag procedure sitting in a persona that should be a skill, and skills small enough to be one persona line.
3. Sort each finding with the initiative ladder: do-then-tell, propose, or ask first.
4. Fix the do-then-tell items, each one as the owner of that layer.
5. Update the Improvement backlog: new proposals at the top, finished lines removed, and a "Done on ‹date›" list of what was fixed.
6. Add a dated lesson to the chief of staff's Lessons.

## Output

A report in chat: what changed, what is proposed and why, and every ⚑ item, with links.

## Rules

- Never delete, archive, retire or merge anything without my yes.
- Never bulk-edit data rows (tasks, logs, glossary terms). Note the pattern and tidy rows as they're touched.
- Don't raise items the backlog marks as parked.
- Creating or changing an agent, skill or rule is a proposal unless I already said yes.

## Done checklist

- [ ] Every persona, the protocol, the Skills rows and the routing table were read.
- [ ] Each finding is fixed, proposed, or waiting on me.
- [ ] Backlog and Lessons updated.
- [ ] Report sent: what changed, links, every ⚑ item.

## Handoff

Findings inside another owner's layer that need real work go to that owner in the handoff format.
