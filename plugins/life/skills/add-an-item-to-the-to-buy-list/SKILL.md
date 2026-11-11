---
name: |-
  add-an-item-to-the-to-buy-list
description: |-
  Use when I say "I need to buy X" or paste a product recommendation. Adds or updates one To buy row per item, with exactly what to look for in the store. Never buys or pays, and never invents prices, sizes or links.
notion_page_id: 4149439f-1486-81d6-b09e-ea08dcb0b1f5
---

## When to use

When I mention something to buy, or paste advice that names products. One row per item.

## Inputs

- The item, and whatever I said about it: what it's for, size, colour, material, fit, budget, link.
- Missing details stay blank. Don't ask for every field; list the gaps in the report.

## Steps

1. Open the To buy list on the <mention url="https://app.notion.com/p/40c9439f14868174be22ead6e5d4225f" /> page and fetch its schema.
2. Look for a matching row first. If one exists, update it; don't add a duplicate.
3. Fill one row per item:
   - **Item:** short name plus its purpose, e.g. "Black belt (slacks)".
   - **Specs:** exactly what to look for: size, colour, material, fit.
   - **For:** what it goes with or is for.
   - **Notes:** the one reason or tip worth remembering in the store.
   - **Category**, and only if I give them, **Budget** (₱) and **Link**.
4. Status: move to Shortlisted when I pick a specific product, and to Bought only when I confirm I bought it.
5. A purchase with a deadline ("buy a gift before the 15th") also goes to the task manager.

## Output

- New or updated To buy rows.
- A short reply: what was added or changed, and which rows still have no specs (⚑).

## Rules

- Never buy, pay, check out or enter payment details.
- Never invent a price, size or product link.
- Never mark Bought without my confirmation.

## Done checklist

- [ ] One row per item, no duplicates.
- [ ] Only details I gave are filled in.
- [ ] Gaps listed as ⚑.

## Handoff

Task manager, for purchases with a date.
