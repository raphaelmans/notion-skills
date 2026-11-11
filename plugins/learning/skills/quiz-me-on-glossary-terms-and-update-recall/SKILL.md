---
name: |-
  quiz-me-on-glossary-terms-and-update-recall
description: |-
  Use when I say "quiz me", "test me on ‹subject›" or "what should I review?". Builds a multiple-choice quiz from the Glossary, asks one question at a time, then updates each term's Recall and Last reviewed. Not for adding or cleaning up terms.
notion_page_id: 4149439f-1486-8191-8d59-cd31cf4d9275
---

## When to use

When I want to practise or review terms. Adding, merging or fixing terms is the glossary keeper's everyday job and doesn't need this skill.

## Inputs

- A filter: subject area, subtopic, layer, or "weak terms". Default: weak terms.
- Number of questions. Default: 8.

## Steps

1. Fetch the Glossary database's schema, then read the rows that match the filter. For "what should I review?", pick up to 10 terms: Weak first, then the longest since Last reviewed, then New.
2. Build the questions, mixing these types:
   - definition → term
   - term → definition
   - example → term ("which concept is this?")
   - don't-confuse pairs ("A or B?")
3. Take the wrong answers from the same Topic, so they're plausible.
4. Ask one question at a time. After each answer, say whether it was right and explain it in plain language.
5. When the quiz ends, update every quizzed term: set Recall using the table below, and Last reviewed to today.
6. Report the score and the terms that are now Weak.

## Recall levels

| Recall | Meaning | Set when |
| --- | --- | --- |
| New | Never quizzed | Row created |
| Weak | Missed or guessed | Wrong answer |
| OK | Right, with some hesitation | Right once after Weak, or right on a hard question |
| Strong | Reliably right | Right twice in a row |

## Output

- The quiz, in chat.
- Recall and Last reviewed updated on each quizzed term.
- A short report: score and Weak terms.

## Rules

- In this job, change only Recall and Last reviewed.
- Never delete a term.
- Never create Tasks. Recurring practice goes to the task manager: "Schedule a 15-minute Glossary review for ‹subject area›."

## Done checklist

- [ ] Every question was answered or skipped by me.
- [ ] Recall and Last reviewed updated for each quizzed term.
- [ ] Score and Weak terms reported.

## Handoff

If the same terms stay Weak across quizzes, tell the learning coach: "These terms keep coming up Weak: …".
