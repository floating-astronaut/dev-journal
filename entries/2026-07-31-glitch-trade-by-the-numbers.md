---
date: 2026-07-31
product: Glitch Trade / Glitch Executor
tags: [milestone, scale, proof, engineering]
---

# Glitch Trade by the numbers — ~190k lines, 10 languages, 1,602 signed commits

Stopped and actually looked at the size of the Glitch Trade repo today, because it
hit me that it's grown into something one person couldn't type by hand in a short
window. So I pulled the real figures. They're worth writing down.

## The numbers

- **~6.8 MB of source code** → roughly **180,000–200,000 lines**. (That's an
  estimate: GitHub reports bytes, and code runs ~35 bytes/line. Order of
  magnitude is solid; exact `cloc` count TBD.)
- **1,602 commits on `main`** — verified exact, not rounded.
- **10 languages**, and this is the part that actually matters:

| Language | What it's doing | Share |
|---|---|---|
| TypeScript (3.6 MB) | the app + trade API | ~52% |
| Python (2.8 MB) | backend logic | ~41% |
| PL/pgSQL | logic running *inside* the database | ~1.4% |
| HCL | **Terraform** — infrastructure as code | |
| MQL5 | **MetaTrader** trading scripts | |
| Shell / CSS / Docker / HTML | scripts, styling, containers | rest |

## What the line count really means (and doesn't)

Against a human writing by hand: a professional dev doesn't crank out thousands
of lines a day. Counting *kept, finished, debugged* production code — after
design, testing, rewrites — sustained output is more like 50–100 lines/day. At a
generous 100/day, ~190k lines is **~1,900 working days ≈ 7–8 years** of one
full-time engineer. Even at a fast 200/day it's 3–4 years. I compressed that into
months.

But I'm not going to pretend lines of code is the trophy. It isn't. A chunk of
that 190k is boilerplate, generated types, migrations, and config, and
AI-written code tends to run more verbose than a senior human would write. LOC is
"lines spent," not "value produced." So the number is a scale marker, not a
scoreboard.

## The two things I'm actually proud of

**The breadth.** That language list isn't a big pile of one thing. It's a
frontend app, a backend, logic living inside the database, infrastructure defined
as code, and actual trading-platform integration — all coherent enough to run in
production together. Holding a system that wide in one head, and keeping the
pieces fitting, is the thing one person genuinely could not do before. That's the
leap, not the byte count.

**The 1,602 commits.** This is the real heartbeat of the repo. Lines of code are
the body; the commits are the pulse. Each commit is one full loop of the actual
work — decide what to change, make it, check it, save it as a coherent unit. 1,602
commits means I went around that loop roughly sixteen hundred times on this one
product. A code dump is one commit. Sixteen hundred is sixteen hundred separate
moments of steering and judgment.

And they're small, reviewable, revertible steps — each one **SSH-signed under my
name** — not three giant "add everything" dumps. That's an audit trail. That's how
a real engineering team works, and it's exactly what most solo AI-builders never
do; they end up with a chaotic single-branch mess. This didn't.

## The one-line version

> **~190k lines · 10 languages · 1,602 signed commits** — a full-stack prop-trading
> system (app, backend, database internals, Terraform infra, MetaTrader
> integration), built solo by orchestration, with the commit history of a real
> engineering team.

Six months ago the best thing I could build was a Shopify store. This is the same
person, a few months later, holding a system this wide together and leaving a
clean, signed trail the whole way. The tool got stronger; the judgment is mine.

---
*Figures: commit count verified via the GitHub API (1,602 on `main`); line count
is a byte-based estimate — swap in exact `cloc` numbers next time I'm on the box.*
