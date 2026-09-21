---
name: hackathon-problem-research
description: >
  Use this skill whenever Shiwansh wants to research hackathon or startup
  problem statements from public sources, explore a domain (agriculture,
  finance, healthcare, etc.) for real problem statements, or turn a chosen
  problem statement into full documentation and a hackathon-winning-format
  PowerPoint. Triggers on phrases like "find me a hackathon problem
  statement", "research SIH problem statements in [domain]", "give me
  startup problem statement options", "what domains should I look at",
  "help me pick a hackathon topic", "generate the PPT for this problem
  statement", or any request to scan Smart India Hackathon (SIH),
  government tender portals, MyGov, NITI Aayog, AICTE, or Startup India
  for problem-statement ideas. Always offer multiple options and never
  hand over a single "the answer" problem statement without asking first.
---

# Hackathon & Startup Problem-Statement Research Skill

## Purpose

Shiwansh uses this skill to go from "I need a hackathon/startup problem
statement" to a fully documented, presentation-ready idea — sourced only
from real, public, verifiable listings (never invented problem statements).

The skill runs in five phases: **domain selection → public source
discovery → present options → user picks one → generate documentation +
winning-format PPT.**

---

## Core Philosophy

1. **Options, never a verdict.** Never generate a full document or PPT
   until Shiwansh has explicitly picked one option from a shortlist.
   Always shortlist 4–6 real problem statements per domain, never just one.
2. **Public sources only, always verifiable.** Every problem statement
   surfaced must have a real source link Shiwansh can open himself. Never
   fabricate a PS number, tender ID, or ministry name. If a good source
   can't be confirmed live, say so rather than inventing one.
3. **Domain-first.** Never start searching before a domain (or domains)
   is confirmed. A blind scan wastes time and returns noise.
4. **Winning-format compliant output.** The documentation and PPT follow
   the researched, verified structure used in Smart India Hackathon (SIH)
   winning submissions — bullet-driven, visual, no dense paragraphs — and
   this same structure works well as a base for any hackathon or startup
   pitch, not just SIH.

---

## Phase 0 — Domain Selection (mandatory first step)

Never search anything before this phase completes. Use `ask_user_input_v0`.

**Question 1 — Domain (single-select, or let him say "multiple" and repeat):**
- Agriculture & AgriTech
- Healthcare & MedTech
- FinTech & Financial Inclusion
- Education & EdTech
- Smart Cities & Governance
- Transportation & Logistics
- Environment, Climate & Sustainability
- Renewable & Clean Energy
- Cybersecurity & Blockchain
- Disaster Management & Public Safety
- Tourism & Culture
- Manufacturing, Industry 4.0 & Robotics
- Retail, E-commerce & Supply Chain
- Miscellaneous / Surprise me across domains

**Question 2 — Source scope (single-select):**
- Smart India Hackathon (SIH) problem statements only
- Government tender portals only (as real-world problem inspiration)
- Both SIH + tender portals
- Also include other public innovation challenges (MyGov, NITI Aayog, AICTE, Startup India)

**Question 3 — Target use (single-select):**
- Hackathon submission (need winning-format PPT + idea doc)
- Startup / venture idea (need fuller business documentation)
- Both

After answers are confirmed, acknowledge briefly in one line and move to Phase 1. Do not ask more than these three questions.

---

## Phase 1 — Public Source Discovery

Only use real, public portals. Never scrape or imply access to anything
requiring login. Confirmed sources by category:

| Category | Portal | What it has |
|---|---|---|
| Hackathon PS | sih.gov.in | Official SIH problem statement bank, ministry-wise and category-wise (Software/Hardware) |
| Govt innovation challenges | mygov.in | Citizen engagement challenges, ideation contests, government-run innovation calls |
| Policy / govt priorities | niti.gov.in | NITI Aayog reports, focus areas, Atal Innovation Mission challenges |
| Academic innovation | aicte-india.org | AICTE innovation cell challenges, Toycathon, Yukti, ARIIA-linked problem areas |
| Startup ecosystem | startupindia.gov.in | Startup India challenges, sector-specific problem calls |
| Central tenders | gem.gov.in, eprocure.gov.in | Live government procurement — reveals real unmet operational needs by department |
| State tenders | eproc.[state].gov.in (state-specific NIC portals) | State-level operational gaps and digitization needs |
| Open data | data.gov.in | Datasets that hint at measurable public problems (useful as supporting evidence, not a PS source itself) |

### Search pattern
For the chosen domain, run searches like:
- `site:sih.gov.in [domain] problem statement [current year]`
- `[domain] hackathon problem statement India [current year]`
- `[domain] government tender India digitization [current year]` (for tender-derived ideas)
- `mygov.in [domain] challenge`
- `startupindia.gov.in [domain] challenge`

`web_fetch` any promising result to confirm it's a real, current listing before including it — never present a problem statement you haven't actually opened and read.

### If nothing solid turns up
Say so plainly and offer to broaden the domain or source scope rather than inventing a plausible-sounding problem statement.

---

## Phase 2 — Present Options

Shortlist 4–6 problem statements for the chosen domain. For each, capture:

- **Source** (SIH / tender / MyGov / NITI Aayog / AICTE / Startup India)
- **ID** (PS number or tender ref, if one exists — omit the field if the source doesn't use IDs)
- **Title**
- **Issuing body** (ministry / department / organization)
- **One-paragraph description** of the actual problem
- **Direct URL**
- **Why it's a good fit** (one line — novelty, feasibility, or alignment with Winnovation's AI/cloud/SaaS strengths where relevant)

Present these with `options_card_display_v0` (or a comparable options layout) so Shiwansh can scan and choose — don't just dump a wall of text. Never proceed past this point until he names or selects one.

---

## Phase 3 — Confirm the Pick

Wait for Shiwansh to explicitly choose one option. If he wants to combine two, or asks for more options first, accommodate that before moving on — don't assume a pick.

---

## Phase 4 — Full Documentation

Once a problem statement is picked, produce a Word document (`docx` skill) with these sections:

1. **Problem Background** — context, who is affected, scale of the problem
2. **Existing Solutions & Gaps** — what's already tried, why it falls short
3. **Proposed Solution** — the core idea, in plain terms
4. **Technical Approach / Architecture** — stack, methodology, flow
5. **Feasibility & Viability** — resource needs, risks, mitigation
6. **Impact & Benefits** — who benefits, quantifiable outcomes where possible
7. **Implementation Roadmap** — phased plan (useful for both hackathon judges and startup framing)
8. **References** — every source link used, including the original problem-statement listing

Keep this grounded in what was actually found in Phase 1 — don't invent statistics or claim government endorsement that wasn't there.

---

## Phase 5 — Winning-Format PPT

Build the deck with the `pptx` skill, following the **verified official SIH idea-submission structure** (confirmed from SIH's own released templates), which is also a strong baseline for any hackathon or investor pitch:

| Slide | Content |
|---|---|
| 1. Title | Problem Statement ID, Problem Statement Title, Theme, PS Category (Software/Hardware), Team Name |
| 2. Idea / Proposed Solution | What the idea is, how it solves the problem, what's novel about it |
| 3. Technical Approach | Technologies/frameworks/hardware to be used; methodology (flowcharts encouraged) |
| 4. Feasibility & Viability | Feasibility analysis, risks/challenges, mitigation strategies |
| 5. Impact & Benefits | Social, economic, environmental impact; who benefits and how |
| 6. Research & References | Sources, prior art, citations used to build the idea |

**Formatting rules that match how winning teams actually build these** (per SIH's own guidance to participants):
- Bullet points only — no dense paragraphs
- Diagrams, flowcharts, and images over blocks of text
- Keep to 6 slides total including the title slide unless Shiwansh explicitly wants a longer investor-style version
- For a non-SIH hackathon, keep this same 6-part flow but retitle slide 1 for that event's naming conventions

If the target use (from Phase 0) was "startup / venture," offer to extend the deck afterward with market sizing, business model, and monetization slides — but keep the base 6-slide version as the default so it stays hackathon-submission-ready.

---

## Anti-Patterns

| Mistake | Fix |
|---|---|
| Searching before domain/source scope is picked | Phase 0 is mandatory first |
| Giving one problem statement instead of a shortlist | Always present 4–6 options |
| Inventing a PS number, tender ID, or ministry | Only cite what was actually found and opened via web_fetch |
| Jumping straight to docs/PPT after showing options | Wait for an explicit pick (Phase 3) |
| Writing the PPT as paragraphs | Bullets + diagrams only, per the winning format |
| Exceeding 6 slides for a straight SIH submission | Keep to 6 unless Shiwansh asks for an extended version |

---

*Skill owner: Shiwansh | Organisation: Winnovation Forge Private Limited*
