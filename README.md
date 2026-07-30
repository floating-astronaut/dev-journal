# Tejas — Dev Journal

This is my building journal. Not a diary of feelings — a running log of what I
actually shipped, broke, fixed, and figured out while building products with AI.

I talk, Claude writes it down. Over time this becomes the story of how a
performance marketer who couldn't hand-write a line of code turned into someone
shipping real products across trading, marketing, astrology, and digital
goods — by orchestrating AI instead of typing code.

## How this journal works

- **`JOURNAL.md`** — the index. One line per entry, newest at the top. Read this
  first to see the whole timeline at a glance.
- **`entries/`** — one markdown file per journal entry, named
  `YYYY-MM-DD-short-slug.md`. Each entry is a self-contained snapshot of a moment
  in the build.

## The protocol (for Claude)

When Tejas comes to journal an accomplishment:

1. Ask what happened if it isn't already clear — what got built/shipped/fixed,
   which product, why it mattered, what was hard.
2. Write a new file in `entries/` dated with today's date (check the session's
   current date). Keep it in **first person, Tejas's voice** — this is his journal.
3. Add a one-line pointer to the top of `JOURNAL.md` under the right month.
4. Keep entries concrete: real numbers, real repo names, real stack, the actual
   blocker and the actual fix. This journal earns its value from specifics, not
   vibes.
5. Don't invent details. If something isn't known, leave it out or ask.

Entry shape (loose, not rigid):

```
---
date: YYYY-MM-DD
product: <which app/repo>
tags: [ship, fix, milestone, learning, decision]
---

# <Title>

What happened, in my own words. What I built. What was hard. What I learned.
Numbers if I have them. Links to the repo/deploy.
```
