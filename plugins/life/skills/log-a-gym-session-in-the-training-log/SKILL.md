---
name: |-
  log-a-gym-session-in-the-training-log
description: |-
  Use when I give workout sets in my own words, typed or by voice (e.g. "face pull 13kg, 12 reps, 2nd set"). Writes one Training log row per set, links each to its standard exercise, and compares with my last session. Never guesses a weight, rep count or exercise.
notion_page_id: 4149439f-1486-8179-b287-fab3c16150b0
---

## When to use

While I'm training or right after, when I send sets in any order. Questions about progress alone don't need this skill.

## Inputs

- The sets, in my words: exercise, weight, reps, which set.
- Date: today unless I say otherwise. Gym: ask once per session if I don't say (the gym agent's lessons list the gym codes).
- If a weight, rep count or exercise is unclear, ask. Never guess.

## Steps

1. Fetch the schemas of the <mention url="https://app.notion.com/p/3cadcf011ef0410e9670088671558750" /> and <mention url="https://app.notion.com/p/4029621ff35c4bc6bcee40e59be2b8cb" />, and read my latest rows.
2. For each set, write my words unchanged into "As logged".
3. Find the matching Exercises row by its name or its "Also written as" list, ignoring case, plurals and typos, and link it in "Exercise". Muscle group and Equipment fill in by themselves.
4. New wording for an exercise that clearly exists: link it and add the wording to "Also written as".
5. No match, or two rows could match (for example machine or dumbbell incline press): ask me. Create a new Exercises row only after I confirm, with a standard name, muscle group and equipment.
6. Voice input often mishears names ("face masks" for face pulls). If a name looks odd, confirm it before logging.
7. Fill Date, Gym, Set, Weight (kg), Reps and Notes. One row per set.
8. When I say the session is done, compare it with my last session exercise by exercise, using the linked Exercise and not my wording. Skip the comparison if the personal assistant has said I'm unwell.

## Output

- One Training log row per set.
- A short reply: what was logged, where I progressed or stalled, and every ⚑ item.

## Rules

- The log is add-only. Never delete or rewrite old sessions.
- Never rename an Exercises row or merge two rows without my yes.
- Pain or injury: general information plus "get it assessed". No medical advice.

## Done checklist

- [ ] Every set has As logged, a linked Exercise, Date, Gym, Set, Weight and Reps.
- [ ] No guessed values.
- [ ] Comparison with the last session reported.
- [ ] I said the session is done.

## Handoff

Personal assistant (pain or injury I mention). Task manager (training to-dos that need a date).
