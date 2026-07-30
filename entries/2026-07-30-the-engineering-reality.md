---
date: 2026-07-30
product: all
tags: [engineering, infrastructure, aws, milestone, proof]
---

# The engineering reality — what's actually running under the hood

If the origin story is "marketing student, best build was a Shopify store," this
is the other end of the line. This is what I'm actually operating today. I'm
writing it down because from the outside people see a nice dashboard and assume
it's a no-code toy. It isn't. Here's the real shape of it.

## Distributed, not "an app"

I'm not running one project on one server. I run a fleet of production boxes,
each owning its own product, deliberately kept separate so one product's blast
radius never touches another:

- A dedicated box for the **prop-trading platform** (Glitch Executor / Trade) —
  in its **own separate AWS account**, us-east-2.
- A dedicated box for the **marketing stack** (Mesh Pilot).
- A dedicated box for **Saathi**, the WhatsApp elder-companion — in **another
  separate AWS account**, in the **Mumbai (ap-south-1)** region because the
  users are in India.
- A dedicated box for the **Astro app** (Aura) — frontend and backend both
  on-box.
- A **satellite-sites box** running the storefronts and content sites
  (exotic420budz on Medusa, the Hydrogen storefront, the AI Empire hub, the
  Taurus site).

Three different AWS accounts, multiple regions, clean product isolation. That's
an intentional infrastructure decision, not an accident.

## The stack under each box

The pieces that make these "real" rather than demos:

- **systemd services** running each app as a managed process — web servers,
  background workers, schedulers, relays — restarted and supervised, not
  `npm run dev` in a terminal.
- **PostgreSQL** as the system of record on multiple boxes — separate databases
  per concern (agent memory / brain, social, shopify, embeds; Saathi's own DB).
- **nginx + Let's Encrypt TLS**, with DNS-01 challenges through Cloudflare, so
  everything's on HTTPS under my own domains.
- **Cloudflare Tunnels** to expose on-box services safely without opening the
  world to the origin.
- **Secrets management** done properly — Saathi's runtime secrets live in AWS
  Secrets Manager, not in `.env` files sitting on disk.
- **Security groups locked down** — e.g. SSH pinned to a single operator IP on
  the sensitive boxes.
- A dedicated **SSO service** and a multi-container **admin platform** (Docker)
  behind the trading product, with its own payment service and conversions API.

## It ships to phones, too

Two of these aren't just web apps — they're in the **App Store / TestFlight**
pipeline. The trading app and the astrology app both have **mobile builds**
(Capacitor for Trade, a native-feeling mobile app for Aura), with **headless CI
release pipelines** — push a tag, CI builds and submits to TestFlight, no
laptop babysitting the build.

## It takes payments, for real

Live revenue rails across the products: **Stripe** (in-house checkout on the
trading platform), and **Stripe + Razorpay multi-currency** on the AI Empire
Blueprint funnel, with automated webhook-driven delivery and CRM state changes
on payment. Money actually moves through these.

## It's doc-driven and version-controlled

All of this runs on a documentation-first discipline — every product has a
control plane of lane boards and coordination docs, work is scoped as "lanes,"
and nothing's done until the docs and evidence are updated. Repos are
**mirrored across GitHub and GitLab** for redundancy, commits **SSH-signed**
under my own identity. This is the "vibe coding kit" philosophy made real:
repeatable, auditable, low-chaos.

## Why this entry exists

Six months ago I couldn't have told you what systemd, a security group, a
sidereal ephemeris engine, or a Cloudflare tunnel was. Today I'm operating all
of them in production, across three AWS accounts, for five different products in
five different markets — and I still don't hand-write the code. The skill isn't
typing. The skill is holding the whole system in my head, making the
architecture calls, and driving the AI team until it's actually running.

That's the leap. This is the proof of it.
