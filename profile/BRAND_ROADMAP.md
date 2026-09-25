# GitHub Personal Brand Roadmap

## Goal

Turn the GitHub account from a repository archive into a coherent public identity:

> **Kevin Meng — AI Builder**
>
> AI Agents × Risk Intelligence × Knowledge Infrastructure × Product Engineering

The profile should answer five questions within one minute:

1. Who is Kevin?
2. What problems does he repeatedly work on?
3. What has he actually built?
4. What makes his approach distinctive?
5. What should I follow or contact him for?

---

## P0 — Fix the first impression

### 1. Create the GitHub Profile repository

Create a public repository named exactly:

`kevin-meng`

Add `README.md` and use `profile/README.md` from `kevin-meng.github.io` as the initial content.

### 2. Update GitHub Bio

Recommended:

`AI Builder · Agent Systems · Risk Intelligence · Knowledge Infrastructure`

### 3. Replace the six pinned repositories

Recommended order:

1. `zeroclaw-hindsight-v2`
2. `financial_stock_knowledge_graph`
3. `toastmaster_tools`
4. `HuggingfaceDownloadShare`
5. `thinking_mentor`
6. `graph_in_life`

Principle: prioritize original work and projects that reinforce the current brand. Do not use forks as flagship work.

### 4. Reduce public repository noise

Review these first:

- `temp` — archive/private/delete if no longer useful
- `featlab` — empty/placeholder; archive or make private
- `zeroclaw-hindsight` — superseded by v2; archive and point to v2
- `toastmaster_timer_tools` vs `toastmaster_tools` — choose one canonical project
- old infrastructure/demo repositories — keep searchable, but archive when they no longer represent maintained work

Do not mass-delete history. The goal is to separate **active / representative / historical** projects.

---

## P1 — Upgrade the flagship repositories

Focus on only 3 repositories first:

### A. zeroclaw-hindsight-v2

Make this the current AI/Agent flagship.

README should clearly show:

- Problem
- Why long-term memory matters
- Architecture diagram
- 3-minute quick start
- Example retain / recall / reflect flow
- Screenshots or terminal demo
- Design trade-offs
- Roadmap

### B. financial_stock_knowledge_graph

This already has public traction and should become a polished long-term asset.

Improve:

- English + Chinese opening summary
- architecture/data-flow diagram
- screenshots
- current status / maintenance note
- reproducible quick start
- sample graph queries
- a short retrospective: what was learned and what would be redesigned today

### C. toastmaster_tools

Position it as a product case study, not only code.

Add:

- user problem
- workflow before / after
- screenshots/GIF
- product decisions
- AI-assisted reporting flow
- local-first/privacy notes where applicable
- roadmap and demo

---

## P1 — Build a recognizable visual system

Use the same system across flagship repositories:

- clean hero
- one-sentence value proposition
- consistent section order
- consistent screenshot framing
- limited badge usage
- same terminology for AI / data / knowledge work

Avoid:

- excessive badges
- animated typing effects
- giant tech-logo walls
- generic GitHub stats cards
- decorative content that says nothing about the work

The desired feeling is **senior builder / product engineer**, not “developer profile template”.

---

## P1 — Rebuild the personal website

`kevin-meng.github.io` currently reflects an older stage of the portfolio.

Turn it into a lightweight personal site with:

- Home
- Projects
- Writing
- Now
- About

The website should expand the story that GitHub starts.

GitHub = proof of work.
Website = narrative and case studies.

---

## P2 — Create a unique public flagship

The biggest future opportunity is a project that connects Kevin's strongest domains instead of treating them separately.

Recommended direction:

### AI × Risk Intelligence

Build a clean-room open-source project using public or synthetic data, for example:

- credit-risk model evaluation toolkit
- model replacement / swap-in-swap-out evaluator
- drift + adversarial validation toolkit
- ranking-focused risk modeling benchmark
- AI agent for model review and experiment documentation

Important: build from public/synthetic data and generic methods. Do not publish employer code, thresholds, proprietary variables, internal data, or confidential process details.

This project can become the strongest bridge between the existing risk background and the future AI direction.

---

## P2 — Make OpenHI a public long-term thesis

Potential repository:

`openhi` or `open-human-intelligence`

Start small:

- manifesto
- principles
- knowledge lifecycle
- architecture ideas
- experiments
- links to related projects

Core loop:

`knowledge → structure → connection → reuse → intelligence`

It does not need to start as a large software platform. A clear thesis plus small working experiments is more credible.

---

## Content rhythm

Do not optimize for contribution-calendar greenness.

A better cadence:

- 1 meaningful public release / month
- 1 technical note or case study / month
- keep 2–3 flagship repositories actively maintained
- archive abandoned experiments clearly
- turn finished experiments into short retrospectives

Quality and continuity create a stronger brand than raw commit count.

---

## Target perception

After the redesign, a visitor should leave with this impression:

> Kevin builds AI-native systems that connect agents, data, risk decisions, and reusable knowledge — and he tends to turn experiments into real tools and products.

That is the brand to reinforce consistently.
