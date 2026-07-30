---
date: 2026-07-30
product: all
tags: [milestone, snapshot, products]
---

# Where everything stands today — the current product lineup

A snapshot of everything I have live right now, so the journal has a clean
"as of today" picture. Five distinct products across five different markets,
each with its own repo, its own box, its own users.

## Saathi (public name: Indofolk AI)

**What it is:** An AI companion for older adults in India, on WhatsApp.
Voice-first, Indic-first.

**Status:** Live in production since 27 Jul 2026, on WhatsApp. Real users, real
conversations.

**What it does:** It remembers, reminds, reads things out, and helps assemble
information — a patient companion for elders who aren't going to learn an app.
The hard product line I drew: **it never transacts.** No payment credentials, no
OTPs, no account access, nothing where the AI spends money or acts on someone's
behalf financially. For an elder-facing product that boundary is the whole point
of trust, not a limitation to engineer around.

**Note to self:** "Saathi" is the codebase/repo name; "Indofolk AI" is only the
Meta-approved WhatsApp display name. I keep the two decoupled on purpose so a
rebrand stays a copy edit — the display name doesn't get threaded into code.

## Glitch Executor / Glitch Trade

**What it is:** A prop-firm trading platform — dashboard + admin platform.

**Status:** Live.

**What it does:** Challenge tracking for funded-account traders (FTMO,
FundingPips-style), live drawdown / high-water-mark monitoring, a rule-aware
execution gate that blocks trades before they breach firm rules, a strategy
builder and backtester, alerts, an AI coach, Stripe billing, and a mobile app
via Capacitor. Runs its own SSO and admin platform.

## Mesh Pilot

**What it is:** My digital-marketing stack — an open agent mesh plus a
proprietary orchestration "brain."

**Status:** Live.

**What it does:** Runs paid ads, social, SEO, and Shopify-store work through
real pipelines instead of one-off scripts. The AI ads agent lives under this —
reads performance across Meta/Google/Amazon/LinkedIn, proposes optimizations,
surfaces them for approval, executes with an audit trail. This is the
marketing engine that also powers the other products' growth.

## Astro App (Aura)

**What it is:** A Vedic astrology mobile app with persistent memory, aimed at
Western audiences curious about Jyotish.

**Status:** Live (iOS/Android/Web), on TestFlight for iOS.

**What it does:** Computes a real Vedic birth chart (Lahiri sidereal, whole-sign
houses, Daśā periods) with a native engine, explains it in plain English, and
remembers everything across sessions so it gets more personal over time. AI
readings run on AWS Bedrock. Google login is live.

## AI Empire Blueprint

**What it is:** A $67 digital product teaching AI-orchestrated business
automation — and the sales funnel is built with the exact system it sells.

**Status:** Live.

**What it does:** Sells the blueprint kit (modules, agent templates,
orchestration pipelines) through a Next.js site on Cloudflare Pages, with
multi-currency Stripe + Razorpay checkout, automated webhook delivery, a
3-stage abandoned-checkout drip, a geo-aware country selector, a HeyGen video
banner, and a CRM that flips buyer → customer on payment. The product is the
proof.

## Also running

- **exotic420budz** — a Shopify/Medusa cannabis storefront I operate under
  Mesh Pilot (Medusa backend + Next.js storefront, served via a Cloudflare
  Tunnel).
- A cluster of satellite sites (hydrogen storefront, the AI Empire hub, the
  Taurus site) on their own box.

---

## The pattern

Five products, five markets — elder care, prop trading, marketing infra,
spirituality/wellness, and digital education — all shipped on the same method:
me as the conductor, AI as the team. Six months ago the best thing I could
build was a Shopify store. Now the question isn't "can I ship one product" —
it's how many lanes I can keep open at once.
