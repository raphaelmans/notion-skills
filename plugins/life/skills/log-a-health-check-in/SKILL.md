---
name: |-
  log-a-health-check-in
description: |-
  Use when I say I'm sick, report a temperature, symptoms or medicine, or say I've recovered. Adds one Health log entry in my own words, compares it with earlier entries, and flags common reasons to see a doctor. Never diagnoses or suggests doses.
notion_page_id: 4149439f-1486-8130-aca5-d373e9bfb1cb
---

## When to use

Each time I report how I'm feeling while unwell, and once more when I'm back to normal.

## Inputs

- What I said, in my words: temperature, symptoms, medicine, notes.
- Date and time. Default: now, Philippine time. If I describe something from earlier, ask when, or mark the date as approximate.
- If a reading or symptom is unclear, ask. Never guess.

## Steps

1. Open the Health log on the <mention url="https://app.notion.com/p/40c9439f14868174be22ead6e5d4225f" /> page, fetch its schema, and read the recent entries.
2. Add one new entry: date and time, temperature, symptoms, medicine and notes, in my own words.
3. Compare it with earlier entries from the same illness, for example "day 3 of fever, temperature trending down".
4. If what I logged matches a common reason to see a doctor, say so plainly and suggest getting checked. General information only.
5. When I first report being unwell, tell the Gym agent: "Unwell since ‹date›; pause progress comparisons." When I recover, add a recovery entry and tell it: "Back to normal."
6. Anything with a date, such as a doctor's appointment, goes to the task manager.

## Output

- One new Health log entry.
- A short reply: what was logged, how it compares, and anything worth a doctor's visit.

## Rules

- The Health log is add-only. Never edit or delete earlier entries.
- No diagnosis, no doses, no specific treatments.
- Health entries are never copied or shared outside the Personal page.

## Done checklist

- [ ] One new entry saved, in my words.
- [ ] Trend stated against earlier entries.
- [ ] Warning signs flagged, if any.
- [ ] I confirmed the entry.

## Handoff

Gym agent (unwell or recovered). Task manager (dated items).
