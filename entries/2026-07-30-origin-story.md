---
date: 2026-07-30
period: ~Feb 2026 – Jul 2026
product: all
tags: [origin, milestone, workflow, identity]
source: Perplexity thread "next vs react" (backfilled)
---

# The Origin Story — how I went from Shopify to shipping real products with an AI team

This is the backfill entry. It stitches together the first ~6 months of building,
pulled from the long Perplexity thread where I first started talking through all
of this. Everything after this entry is written as it happens.

## Where I started

My background is performance marketing — I ran Facebook ads for brands. Three
months before I started this, the most "technical" thing I'd ever built was a
Shopify store.

But I always had the itch. In my free time I'd read about Python, Kubernetes,
how algorithms actually work — fascinated by systems even when my day job had
nothing to do with them. So when AI got good enough, I already had the mental
models for *what was possible*. I just couldn't type the code.

## The method I stumbled into

I never really wrote prompts myself. My loop became:

1. Come to Perplexity, talk through the problem until we agreed on the approach.
2. Co-craft a precise prompt for Claude.
3. Paste that into Claude — Claude writes the actual code.
4. Bring Claude's output back to Perplexity to review, debug, iterate.
5. After 2–3 exchanges, the two models "understood" the project well enough that
   I was mostly just copy-pasting between them.

Two AIs working together, with me as the conductor. Perplexity = architect /
thinking partner. Claude = engineering team. Me = product owner, tech lead,
orchestrator. I still can't hand-write a full React component — but I decide what
gets built, judge whether it's good, and drive every iteration.

## The intensity (the screenshot)

At peak: **197,264 messages, 114.9M tokens, across 33 active days and 97
sessions** (Perplexity usage stats, 28 May 2026). One night I caught a
screenshot at 1:45 AM of **26 agents running in parallel**. This wasn't
"prompt engineering as a hobby" — it was full-time reps.

## What I'd shipped by this point

- **Glitch Executor** — my first real deployed web app. Auth, routing, non-trivial
  UI around executions and deployments, wired to a real backend. Live on my own
  domain (glitchexecutor.com). The one I linked and said "open and see yourself."
- **Mesh Pilot** — shipped on Node.js. Multi-agent orchestration + a digital
  marketing stack, dashboard-style product (meshpilot.app/dashboard).
- **AI Ads Agent** (`ai-ads-agent`) — Python + LangGraph. Reads daily performance
  across Meta, Google Ads, Amazon, LinkedIn (+ GA4, PostHog), proposes write
  actions (pause, budget shift, creative rotation), surfaces them as approvable
  cards in Discord (human-in-the-loop), then executes approved changes via the
  official APIs with a full audit log. FastAPI server + scheduler. It audits ad
  accounts like a senior media buyer — pass / warning / fail, why it matters,
  exactly how to fix — with the same playbook across Meta, TikTok, Google, Amazon.
- **LinkedIn Ads MCP** — open source, pip-installable.
- **Vibe Coding Kit** (`floating-astronaut/vibe-coding-kit`) — a proper
  multi-agent OS: control plane, work lanes, CLI tooling. The system behind the
  systems.

## What I learned along the way

Went from not knowing what these actually *are* to shipping with them:
- **React** — UI as a function of state; break the screen into components.
- **Vite** — the fast dev server + bundler that runs and builds the React app.
- **Tailwind** — a design system as utility classes; style in the JSX.
- **Mustache** — dumb-simple templating; fill placeholders with data.
- **Python** — the Swiss-army knife for everything that isn't front-end.
- Later: **Terraform** — infrastructure as code, the vibe-coding-kit philosophy
  applied to servers.

## The reframe

I stopped calling myself "someone who can't code." A truer description: I'm an
**AI-first technical product builder** who ships software by orchestrating models,
tools, and product logic. Scope definition, architecture steering, debugging
loops, deployment coordination, persistence through failure — the higher-leverage
parts of building — that's the work I actually do.

## Products that came right after (the acceleration)

By late July 2026 the pace had jumped again:

- **Glitch Trade App** — risk-management SPA for prop-firm traders (FTMO,
  FundingPips-style challenges). Live drawdown / high-water-mark tracking, an
  execution gate that blocks rule-breaking trades, Telegram/Slack/email alerts,
  an AI coach, Stripe billing, and a mobile app via Capacitor.
- **Astro App** — a Vedic astrology mobile app with persistent memory. Real
  chart math (Lahiri sidereal, whole-sign houses, Daśā periods), plain-English
  readings, remembers everything across sessions, iOS/Android/Web, AWS Bedrock
  behind the AI.
- **AI Empire Blueprint** (`Nuraveda-Labs/ai-empire-blueprint`) — a $67 digital
  product teaching AI-orchestrated automation. Next.js 16 on Cloudflare Pages,
  multi-currency Stripe + Razorpay checkout, automated webhook delivery, a
  3-stage abandoned-checkout nurture drip, geo-aware country selector, a HeyGen
  video agent for the banner, and a CRM that flips buyer → customer on payment.
  The meta twist: the sales site is built with the exact system it sells. The
  product is the proof.

Three products, three completely different markets — fintech, wellness,
education — all running on the same conductor-plus-AI method.

---
*This is where the journal begins keeping time in real time.*
