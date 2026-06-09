# Verata — Where data meets improvement.

> **Microsoft Agents League Hackathon 2026** · Reasoning Agents Track · Foundry IQ

![Verata](https://img.shields.io/badge/Track-Reasoning%20Agents-0078D4?style=flat-square)
![Foundry IQ](https://img.shields.io/badge/IQ%20Layer-Foundry%20IQ-00A86B?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active%20Build-E07B00?style=flat-square)

---

## What is Verata?

Verata is an AI reasoning agent that helps NGO programme managers understand **why their programmes aren't delivering results** — and what to do about it.

It bridges two disciplines that have never been combined in a single tool:

- **Monitoring & Evaluation (M&E)** — the development sector's framework for tracking programme results through indicators, targets, and actuals
- **Lean Six Sigma DMAIC** — a structured process improvement methodology used to diagnose root causes of underperformance and generate prioritised corrective actions

**The result:** paste your programme data → get a complete diagnostic report in under 60 seconds. No consultant required.

---

## The Problem

NGOs collect mountains of programme data. Most of it goes unanalysed beyond basic target-vs-actual comparisons. Programme managers know something is wrong but cannot pinpoint *why*. Bringing in a consultant costs time and money most NGOs don't have.

Meanwhile, Lean Six Sigma has been diagnosing exactly these kinds of systemic problems for decades — but exclusively in the private sector. **No tool bridges M&E evidence with LSS process improvement logic for the development sector.**

Verata is that bridge.

---

## Demo

**[▶ Watch the 60-second demo](#)** *(link to be added)*

**Live demo:** Open `index.html` in any browser, click **Load demo data**, then **Analyse my programme**.

---

## How It Works — The DMAIC Reasoning Pipeline

Verata processes data through six sequential AI reasoning phases, each building on the last:

```
User pastes programme data (any format)
        ↓
┌──────────────────────────────────────────────────────────────────┐
│  D  Define    Extract programme metadata + indicator list        │
│  M  Measure   Calculate achievement rates + severity scores      │
│  A  Analyse   Root cause analysis ← FOUNDRY IQ                  │
│  I  Improve   Prioritised action plan with effort/impact         │
│  C  Control   KPIs, review triggers + accountability register    │
│  R  Report    Donor narrative + Executive summary                │
└──────────────────────────────────────────────────────────────────┘
        ↓
Complete Verata Report (gap table · root causes · actions · control plan · narrative)
```

### Phase Details

| Phase | Prompt | Foundry IQ | What happens |
|-------|--------|------------|--------------|
| Define | VP-01 | No | Converts raw unstructured input into clean JSON: programme name, goal, period, indicators |
| Measure | VP-02 | No | Calculates achievement rate per indicator; assigns severity (Critical / Moderate / On Track) |
| Analyse | VP-03 | **YES** | Identifies root cause category + 2–3 grounded contributing factors per gap; confidence-rated |
| Improve | VP-04 | No | Generates prioritised actions scored by effort, impact, and timeframe |
| Control | VP-07 | No | Builds a control plan: KPIs to monitor, warning triggers, review frequency, accountable roles |
| Report | VP-05 + VP-06 | No | Donor narrative paragraph + 3-section executive summary (parallel calls) |

### Root Cause Categories (Analyse Phase)

The Foundry IQ-powered Analyse phase classifies every underperforming indicator into one of six categories:

- `process_design` — programme activities or workflow are poorly structured
- `resource_constraint` — insufficient funding, staff, or materials
- `capacity_gap` — staff or beneficiary skills/knowledge are insufficient
- `context_barrier` — external factors (geographic, social, political, seasonal)
- `data_quality` — targets may be unrealistic or data collection is flawed
- `coordination_failure` — partner or stakeholder alignment has broken down

Every finding is grounded in the actual uploaded data — not generic advice. Confidence ratings (high / medium / low) are assigned per finding.

---

## Microsoft IQ Integration

**IQ Layer used: Foundry IQ**

Foundry IQ powers the **Analyse phase (VP-03)** of the DMAIC pipeline — the most critical reasoning step. This ensures:

- Root cause identification is grounded in the user's actual indicator data
- Every contributing factor is cited back to a specific data point
- Hallucinated findings are eliminated through retrieval-augmented reasoning
- Confidence levels are surfaced to the user where data is ambiguous

**Why Foundry IQ for this phase specifically:**
The Analyse phase is where the agent makes its highest-stakes inferences — diagnosing *why* a programme is underperforming. Generic AI reasoning here produces generic advice. Foundry IQ's grounding capability ensures findings are specific, evidenced, and actionable.

---

## Prompt Library

All seven agent prompts are documented in [`/prompts/`](./prompts/):

| File | Phase | Purpose |
|------|-------|---------|
| `VP-01-define.md` | Define | Data extraction & normalisation |
| `VP-02-measure.md` | Measure | Gap calculation & severity scoring |
| `VP-03-analyse.md` | Analyse | Root cause analysis (Foundry IQ) |
| `VP-04-improve.md` | Improve | Improvement action generation |
| `VP-05-narrative.md` | Report | Donor narrative writer |
| `VP-06-summary.md` | Report | Executive summary generator |
| `VP-07-control.md` | Control | Control plan + KPI register |

---

## Export & Output Features

Every Verata analysis produces four export options:

| Export | What it gives you |
|--------|------------------|
| **↓ Download PDF report** | Fully branded report — navy cover, white body, all sections. Open in browser → Print → Save as PDF |
| **✉ Copy email summary** | Pre-formatted email with subject line, performance overview, narrative, and top 3 priorities — paste straight into Gmail |
| **⬡ Generate implementation templates** | Two pre-populated CSV files: Improvement Plan (actions with assignee/date columns) and Control Register (KPIs, triggers, review schedule) — opens in Excel |

---

## Repo Structure

```
verata-agent/
├── index.html              # Full prototype — open in browser to run
├── prompts/
│   ├── VP-01-define.md
│   ├── VP-02-measure.md
│   ├── VP-03-analyse.md
│   ├── VP-04-improve.md
│   ├── VP-05-narrative.md
│   └── VP-06-summary.md
├── docs/
│   ├── VERATA_MASTER_BUILD.md
│   └── VERATA_PROMPT_LIBRARY.md
├── LICENSE
└── README.md
```

---

## Running Locally

1. Clone the repo:
   ```bash
   git clone https://github.com/YOUR_USERNAME/verata-agent.git
   cd verata-agent
   ```

2. Open `index.html` in any modern browser — no build step required.

3. Click **Load demo data** to use the pre-built Limpopo Community Health Access Programme scenario, or paste your own programme indicator data.

4. Click **Analyse my programme** and watch the DMAIC pipeline run.

> **Note:** The prototype uses the Anthropic API directly from the browser. The API call is handled client-side for the hackathon demo. A production version would route through a secure backend.

---

## Built With

- **Microsoft Foundry** — Reasoning Agents track
- **Foundry IQ** — Grounded root cause analysis (Analyse phase)
- **Anthropic claude-sonnet-4** — DMAIC reasoning pipeline
- **HTML / CSS / Vanilla JS** — Single-file prototype, zero dependencies

---

## The Builder

**Genevieve Nahbeelah Dean**
Principal, Dean Process Excellence (DPE) · Co-founder & CTO, MAW Consulting Africa
Certified Lean Six Sigma Master Black Belt (MBB) · MERL Specialist

Verata is built from lived domain expertise — 10+ years spanning process excellence consulting, M&E systems design, and digital product development across the African development sector.

- LinkedIn: [linkedin.com/in/genevieve-n-dean-a313572a](https://www.linkedin.com/in/genevieve-n-dean-a313572a/)
- MAW Consulting Africa: [mawconsultingafrica.com](https://mawconsultingafrica.com)

---

## Licence

MIT — see [LICENSE](./LICENSE). Verata is a product of Dean Process Excellence / MAW Consulting Africa.

---

*Microsoft Agents League Hackathon 2026 · Project #123702*
