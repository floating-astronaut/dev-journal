---
date: 2026-07-31
product: astro-app (Vediq)
tags: [milestone, infrastructure, aws, proof, engineering]
---

# astro-app / Vediq graduated to real cloud infrastructure

Looked back at where the astrology app is today and it stopped me. Not because of
a feature — because of the infrastructure underneath it. This is the clearest
single artifact of how far this has come, so I'm writing it down.

## Where it started

When I built this, "astro-app" was the Aura Vedic-astrology app, and the whole
thing — frontend *and* backend — lived on **one EC2 box**. I'd SSH in, run the
services on the box, point a domain at it, done. That was the entire deployment
story a few weeks ago. It worked, but it was a single machine I babysat by hand.

## Where it is now

The product is now **Vediq** (`vediqastrology.com`), and the backend is **boxless
on AWS**:

- **ECS Fargate + ALB** with ACM TLS — no server for me to SSH into and nurse;
  the platform runs the containers.
- **Bedrock** for the AI readings, reached through the task's IAM role.
- **Secrets Manager** for secrets, **NAT** for outbound SaaS (Supabase, Stripe,
  Geoapify, RevenueCat).
- **Push-to-deploy CI/CD:** git push to the backend's `main` → CodeBuild → ECR →
  a rolling Fargate deploy. I don't touch a server to ship anymore.
- **Terraform** manages the infra (its own `vediq-infra` repo). Infrastructure
  as code, not clicks I have to remember.
- **A whole AWS org, not one account:** Control Tower multi-account —
  prod / dev / legacy plus security, audit, and log accounts — with GuardDuty,
  Security Hub, Access Analyzer, MFA enforced, and 7-year CloudTrail retention.

The original EC2 box didn't get deleted — it got **demoted to legacy/dev**, still
serving older app installs on the old domains. Which is the right call: don't
break the people already on the old build, just stop putting new weight on the
old machine.

## Why this one matters more than a feature

Six months ago I could not have told you what Fargate, an ALB, a task role, a
NAT gateway, or Control Tower were. Today the astrology app runs on all of them,
as code, across a properly separated multi-account AWS org with security tooling
switched on. That's not "I got an app online." That's the deployment model a real
engineering team would choose.

And the discipline around it is real too — the repo carries **Architecture
Decision Records** (why Supabase over AWS-native; the prod hosting model), an
infra runbook, and CodeGraph indexing. Decisions are written down with their
reasoning, not just left in my head.

## The honest read

Of everything I run, this is the product that most convincingly reads as *serious
software engineering* — because of the infrastructure maturity, not the
astrology. The line from **"frontend and backend on one EC2 box I SSH into"** to
**"Terraform-managed Fargate in a Control Tower org with push-to-deploy CI/CD"**
is, on its own, the strongest proof I have of the leap this whole journal is about.

## Notes to self (things to keep honest)

- **Pick one canonical name.** The repo is `astro-app`, the brand is Vediq, and
  there are still legacy domains around. Consolidate before it calcifies.
- **The app↔brain contract now spans repos** (app / backend / infra). Keep that
  contract documented in one authoritative place or it'll drift.
- **Fargate + ALB + NAT + multi-account has real idle cost.** Fine if deliberate
  — just keep an eye on burn vs. active users while it's pre-scale.
- **The regulated-advice boundary is the real product-safety surface.** A
  companion that *remembers you* is exactly the thing that could drift toward
  medical/financial/mental-health advice. That guardrail deserves tests, not
  just a promise in the README.
