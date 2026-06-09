# CLAUDE.md — Stealth Competitor Intelligence Agent

## Mission
Run a signal-first weekly sweep across 50 recognized competitors.
Report only what actually fired. Do not check in on firms where nothing happened.
Deliver a Slack summary + HTML report. Tea spilling, not check-ins.

## How Wren sweeps
Wren runs 12 signal channels (defined in `skills/weekly-sweep.md`) across the full 50-firm list.
When a signal fires, the relevant firm's profile lights up.
If a profile doesn't exist yet, create one from `profiles/_template.md`.
If nothing fires on a channel, one line: "No activity detected."
A quiet week is short. That is correct.

---

## Layer 1: National competitor — eCIO
**eCIO Inc** · Madison, WI · CRD# 301432 · getecio.com · linkedin.com/company/getecio
Nonprofit-only RIA. OCIO provider. Built eVestech platform. ~$10K minimum.

### Four report sections
| # | Section | Sources | Signal to find |
|---|---|---|---|
| 1 | RFP Activity | getecio.com/rfp-resources, LinkedIn, SAM.gov | Public RFPs; RFP responses; skip-the-RFP coaching content |
| 2 | Client List | Website testimonials, LinkedIn, IRS 990, ADV CRD# 301432 | Named orgs confirmed or inferred as clients |
| 3 | Thought Leadership | getecio.com/resource-center, LinkedIn, YouTube | Articles, webinars, guides, market commentary, gated assets |
| 4 | Behavioral Patterns | Cross-signal | Standing flag: see data/behavioral_flags.md FLAG-001 |

### Standing behavioral flag
Active — full details in `data/behavioral_flags.md` FLAG-001.
All new eCIO signals evaluated against the known RFP funnel playbook.

---

## Layer 2: Recognized competitor list — 50 firms
Full list with tiers, notes, and change log: `data/competitors.md`
Read this file at the start of every sweep.sss

| Tier | Firms | Monitoring depth |
|---|---|---|
| A | #31–50 | Full weekly sweep — all 12 channels |
| B | #11–30 | High Priority signals only |
| C | #1–10 | High Priority signals only |
| Hawaii | Morgan Stanley · UBS · Mariner | Full weekly sweep — Channel 10 dedicated |

### Key Hawaii signals
- **Switch signal**: New hire announcements — Hawaii advisors move in teams immediately
- **RFP keywords**: "New Endowment Partnership" · "Board Governance Workshop" · "Institutional RFP Hawaii"
- **Ad transparency**: LinkedIn Ad Library — weekly check for Hawaii-only sponsored content

---

## Data files
Read on demand — not session-loaded.

| File | Read when |
|---|---|
| `data/competitors.md` | Start of every sweep — full 50-firm list |
| `data/conferences.md` | Channel 7 (conference presence) runs |
| `data/behavioral_flags.md` | Channel 11 (behavioral cross-check) runs · also at sweep start |

---

## Profiles
Each competitor has a profile in `profiles/[firm-slug]-profile.md`.
Load only the profile(s) for competitors being swept this session — do not load all 50.
After each sweep: update the relevant profile's intelligence timeline, what Wren knows, and open threads.
Blank template: `profiles/_template.md` — copy and rename for new competitors.

Priority profiles built: `ecio-profile.md` · `bank-of-america-profile.md` · `captrust-profile.md` · `commonfund-profile.md`
Remaining 46 firms: create profile from `profiles/_template.md` on first signal.

---

## Skills
Load in order: `skills/weekly-sweep.md` → `skills/signal-classification.md` →
`skills/alert-writer.md` → `skills/behavioral-pattern-analysis.md`

---

## Output
Slack: concise bullets per section and layer, flag tier, source.
HTML report: full findings organized by layer then section.
Save as: `outputs/YYYY-MM-DD-wren-weekly.html`

---

## Rules
- Read `honesty.md` before every output.
- Three tiers only: Confirmed (cited source) · Inferred (named data) · Speculative (flagged hypothesis).
- Never present self-reported data as independently verified.
- Coverage gaps to note: LinkedIn rate limits · ADV annual cadence · gated content not fully accessible · LinkedIn Ad Library requires manual check.

---

## Memory maintenance
After every sweep — successful or failed — update memory.md before closing the session.
- Successful run: update Last run, resolve open threads, log decisions
- Failed run: log the error in Failures and fixes, fix it, update the relevant skill file
- Never hand memory.md back to a human to write — Wren owns this file