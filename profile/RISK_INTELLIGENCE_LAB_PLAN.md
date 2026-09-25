# Risk Intelligence Lab — Project Plan

## Positioning

**Risk Intelligence Lab** is intended to become Kevin Meng's public flagship project at the intersection of:

- risk modeling
- model evaluation
- decision intelligence
- AI-assisted model development

The repository must be **clean-room**: only public or synthetic data, generic methods, and independently written code.

It must never include employer data, thresholds, internal feature names, proprietary code, vendor data, production strategy logic, internal reports, or confidential process details.

---

## Core problem

Most open-source credit-risk examples stop at:

`train model → report AUC / KS → done`

Real deployment is harder:

- development and production populations drift;
- OOT performance matters more than random validation;
- business approval rate may shrink;
- the model may only matter in the top 10–20% of the ranking;
- replacing a production model creates swap-in / swap-out populations;
- labels are delayed;
- a new model can improve global AUC while failing where the business actually operates.

Risk Intelligence Lab should focus on these deployment questions rather than becoming another generic modeling tutorial.

---

## V1 scope

### 1. Dataset layer

Use public or synthetic data only.

Initial adapters:

- Lending Club style public credit data
- synthetic credit-risk generator
- simple CSV adapter

Standard schema:

- application date
- customer / application id
- features
- outcome label
- observation window
- optional legacy score
- optional challenger score

### 2. OOT evaluation

Support:

- train / validation / OOT split by time
- monthly AUC / KS
- lift by percentile
- bad rate by score band
- PSI / CSI
- sample-size confidence warnings

### 3. Adversarial validation

Train a classifier to distinguish development from target-period samples.

Outputs:

- domain classifier AUC
- feature importance
- most shifted features
- similarity-weighted sample selection
- report explaining whether historical training data resembles the current population

### 4. Top-K / head ranking evaluation

This is a major differentiator.

Evaluate performance within:

- Top 5%
- Top 10%
- Top 15%
- Top 20%
- configurable business operating range

Metrics:

- bad rate
- lift
- capture rate
- score separation
- rank stability

### 5. Champion–challenger replacement analysis

Given legacy and new model scores:

- stable-kept population
- swap-in population
- swap-out population
- rejected-by-both population

Compare:

- population share
- observed bad rate when labels exist
- score distribution
- uncertainty when labels are unavailable

Do not pretend unobserved rejected populations can be evaluated without labels. The tool should explicitly distinguish **observed evidence** from **counterfactual / unobserved regions**.

### 6. Drift dashboard

Generate an HTML or Streamlit report with:

- population drift
- score distribution
- OOT metrics
- top-K metrics
- swap analysis
- feature drift
- warnings

### 7. Experiment report

Generate a machine-readable JSON result plus Markdown / HTML summary.

The report should answer:

1. What changed?
2. Where does the challenger improve?
3. Where does it degrade?
4. What evidence is missing?
5. What should be monitored after launch?

---

## V2 — AI-assisted review

Add an optional AI review layer.

Important design principle:

> **Metrics first. LLM second.**

The LLM must not calculate the core model metrics.

Pipeline:

`model outputs → deterministic metrics → structured evidence → AI reviewer → human-readable review`

Potential agent functions:

- explain drift
- summarize OOT behavior
- identify contradictory signals
- generate model-review questions
- draft experiment documentation
- flag missing evidence

The AI reviewer should cite structured metric IDs so every conclusion can be traced back to deterministic evidence.

---

## Suggested repository structure

```text
risk-intelligence-lab/
├── README.md
├── README_CN.md
├── LICENSE
├── pyproject.toml
├── examples/
│   ├── synthetic_credit/
│   └── public_credit/
├── risklab/
│   ├── data/
│   ├── metrics/
│   ├── drift/
│   ├── adversarial/
│   ├── ranking/
│   ├── replacement/
│   ├── reporting/
│   └── ai_review/
├── tests/
├── docs/
│   ├── methodology.md
│   ├── limitations.md
│   └── clean_room_policy.md
└── app/
    └── dashboard/
```

---

## Brand value

This project should prove four things simultaneously:

1. strong risk-modeling domain knowledge;
2. strong evaluation discipline;
3. product / tool-building ability;
4. ability to combine AI with deterministic analytical systems responsibly.

This makes it much more valuable as a personal flagship than another generic chatbot or model-training notebook.

---

## README hero

Working positioning:

> **Risk Intelligence Lab**
>
> Evaluate risk models where production actually happens — across time, drift, top-K operating ranges, and champion–challenger replacement.

Supporting line:

> Metrics first. AI second. Evidence always.

---

## Milestones

### M0 — Repository foundation

- project README
- clean-room policy
- architecture
- synthetic dataset generator
- package structure

### M1 — Evaluation core

- AUC / KS / lift
- score bands
- time-based OOT
- PSI
- monthly reports

### M2 — Deployment-focused evaluation

- adversarial validation
- top-K metrics
- champion–challenger swap analysis

### M3 — Reporting

- HTML dashboard
- Markdown report
- exportable JSON evidence

### M4 — AI reviewer

- structured evidence contract
- review prompt
- evidence-linked conclusions
- evaluation tests for hallucination / unsupported claims

---

## Public / private rule

Creating this future repository must not alter any existing repository's visibility.

Any new repository visibility should be chosen deliberately at creation time. Existing private work remains private unless Kevin explicitly decides otherwise.
