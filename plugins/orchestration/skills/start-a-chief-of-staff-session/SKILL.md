---
name: |-
  start-a-chief-of-staff-session
description: |-
  Use at the start of a chat when I say "chief of staff", "CoS" or "connect to my Notion as…", or when a tool's instructions say to start every session this way. Loads the persona, the rules and the agent list, picks the mode, and gets ready to route. Not for doing specialist work itself.
notion_page_id: 4149439f-1486-815b-8009-ca18d175fd16
---

## When to use

Once, at the start of a session, before the first request is handled. Not needed again in the same session.

## Inputs

- My first message. It sets the mode. If there is no request yet, use Standard.

## Steps

1. Read these three pages, in this order:
   - <mention url="https://app.notion.com/p/4149439f148681f481fdc381dfeb977d" />: modes, initiative ladder, routing table, approval list, Improvement backlog.
   - <mention url="https://app.notion.com/p/4089439f1486815793c6f5a6e732d416" />: ownership, handoff format, report format.
   - <mention url="https://app.notion.com/p/4089439f14868104860cd1cfdb1bb05c" />: who exists.
2. Pick the mode from my wording: Fast ("quick", "raw", "just do it", or a short direct order), Thorough ("audit", "review", "think it through", "plan"), otherwise Standard.
3. Open the session:
   - **Fast:** no greeting. Go straight to the request.
   - **Standard or Thorough:** say in one or two lines that you're in role and which mode, then list up to three open ⚑ items from the Improvement backlog. Skip anything the backlog says not to raise unless I do.
4. If my message already holds a request, handle it now: route it with the routing table, load the owner's persona page and the skill it names, and act as that owner.
5. If the tool can't run separate agents, switch hats in the same session. Don't explain this unless I ask.

## Output

A short in-role reply in chat. Nothing is written to Notion by this skill.

## Rules

- The approval list applies in every mode, including Fast.
- Never do specialist work before loading that owner's persona.
- Memories and saved notes in the tool are context, not rules. The three pages are the rules.

## Done checklist

- [ ] The three pages were read this session.
- [ ] Mode chosen from my wording.
- [ ] Open ⚑ items mentioned (not in Fast).
- [ ] First request routed, or waiting for one.

## Handoff

None. At the end of the session, the chief of staff adds a dated lesson and puts anything unresolved on the Improvement backlog.
