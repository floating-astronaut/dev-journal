# Dev Journal — Index

The running timeline of what I've built. Newest at the top. One line per entry;
open the file in `entries/` for the full story.

See [README.md](README.md) for how this journal works.

## 2026 — July

- [Glitch Trade by the Numbers](entries/2026-07-31-glitch-trade-by-the-numbers.md) — the scale marker: ~190k lines of code across 10 languages (TS app, Python backend, PL/pgSQL, Terraform/HCL, MetaTrader/MQL5…) and 1,602 signed commits on main. ~7–8 years of one-human output compressed into months — but the real story is the breadth (full-stack + DB internals + infra + trading integration) and the 1,602-commit heartbeat of a human-in-the-loop.
- [astro-app / Vediq Cloud Graduation](entries/2026-07-31-astro-app-vediq-cloud-graduation.md) — the EC2→Fargate leap: from frontend+backend on one SSH'd box to boxless ECS Fargate + ALB + push-to-deploy CI/CD (CodeBuild→ECR→Fargate), Terraform-managed, in a Control Tower multi-account AWS org with security tooling on. The single strongest proof of the engineering leap. Rebranded Aura → Vediq (vediqastrology.com).
- [The Engineering Reality](entries/2026-07-30-the-engineering-reality.md) — proof of the leap: what's actually running under the hood. A fleet of production boxes across three AWS accounts and multiple regions, systemd + Postgres + nginx/TLS + Cloudflare tunnels, AWS Secrets Manager, SSO, Docker admin stack, mobile CI to TestFlight, live Stripe/Razorpay rails, doc-driven and SSH-signed. Not a no-code toy — serious distributed engineering.
- [Current Product Lineup](entries/2026-07-30-current-products.md) — "as of today" snapshot: five live products across five markets — Saathi (Indofolk AI, WhatsApp elder companion, live since 27 Jul), Glitch Executor/Trade, Mesh Pilot, Astro App (Aura), AI Empire Blueprint — plus exotic420budz and the satellite sites.
- [The Origin Story](entries/2026-07-30-origin-story.md) — backfill: Shopify → shipping real products with an AI team. The Perplexity→Claude conductor method, the 197K-message/33-day sprint, and everything shipped by end of July (Glitch Executor, Mesh Pilot, AI Ads Agent, Glitch Trade, Astro App, AI Empire Blueprint, LinkedIn Ads MCP, Vibe Coding Kit).

<!-- New entries go above this line, under the right month heading. -->
