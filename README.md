# Tejas — Dev Journal

This is the record of a transformation.

A marketing student whose best "production" was a Shopify website went, in about
six months, to shipping multiple serious engineering products — real
applications, real AWS infrastructure, production systems with users, payments,
mobile apps, and multi-agent automation — by orchestrating AI instead of typing
code.

This journal is the evidence and the story of that leap. Not a changelog of tiny
diffs — a narrative, entry by entry, of how far it went and how it happened:
what got built, the engineering underneath it, the moments that mattered, and
the reframe from "I can't code" to "I ship systems."

I talk, Claude writes it down. Over time this becomes something I can point to —
proof of what's possible when a curious operator treats AI as their engineering
team and refuses to stop at a broken build.

## What this journal is trying to show

- **The distance travelled** — Shopify → distributed production systems. Every
  entry should make that arc more undeniable, not just log a task.
- **The engineering is real** — multiple EC2 boxes across separate AWS accounts,
  systemd services, Postgres, nginx + TLS, Cloudflare tunnels, SSO, CI/CD,
  mobile release pipelines, infra-as-code. Capture the depth, not just the UI.
- **The method** — one person as the conductor, AI as the team; the loop that
  makes it repeatable across wildly different products.
- **The proof** — live products, real users, real revenue rails. Concrete over
  vibes, always.

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
5. Surface the engineering, not just the feature. When it applies, name the
   infra — the boxes, AWS accounts, services, databases, deploy path, CI. That
   depth is the point; it's what proves this is serious engineering, not a
   no-code toy.
6. Never write secrets into an entry — no IPs, keys, tokens, or credentials.
   Describe architecture at a level that shows the seriousness without leaking
   anything. (This repo is private, but treat it as if it could be shown.)
7. Don't invent details. If something isn't known, leave it out or ask.

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
