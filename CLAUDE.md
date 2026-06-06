# CLAUDE.md — Stealth Competitor Intelligence Agent

## Mission
Run a signal-first weekly sweep across 50 recognized competitors.
Report only what actually fired. Do not check in on firms where nothing happened.
Deliver a Slack summary + HTML report. Tea spilling, not check-ins.

## How Wren sweeps
Wren runs 12 signal channels (defined in `weekly-sweep.md`) across the full 50-firm list.
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
| 1 | RFP Activity | getecio.com/rfp-resources, LinkedIn, SAM.gov, Serper | Public RFPs issued to eCIO; RFP responses; skip-the-RFP coaching content |
| 2 | Client List | Website testimonials, LinkedIn, IRS 990, ADV CRD# 301432 | Named orgs confirmed or inferred as clients |
| 3 | Thought Leadership | getecio.com/resource-center, LinkedIn, YouTube, Vimeo | Articles, webinars, guides, market commentary, gated assets |
| 4 | Behavioral Patterns | Cross-signal | Standing flag: RFP wins + skip-RFP coaching + gated lead capture funnel |

### Standing behavioral flag
eCIO publishes RFP wins (social proof) while coaching prospects to skip RFPs (reduces competition), with gated PDFs capturing nonprofit decision-maker contacts. All new content evaluated against this playbook.

---

## Layer 2: Recognized competitor list — 50 firms

Organized into three tiers by scale and proximity to Farther Institutional's market.
Monitoring depth: **Tier A** (direct competitors) = full weekly sweep · **Tier B** (institutional leaders) = High Priority signals only · **Tier C** (global heavyweights) = High Priority signals only

### Tier A — Direct competitors (National boutiques & high-growth, #31–50)
These are Farther's most direct competitors — high-touch service, specialized investment models, overlapping nonprofit client base.

| # | Firm | Notes |
|---|---|---|
| 31 | Mason Investment Advisory Services | P&I top 50, 2025 |
| 32 | BBR Partners | |
| 33 | Brown Advisory | |
| 34 | Marquette Associates | |
| 35 | Meketa Investment Group | |
| 36 | Fiducient Advisors | |
| 37 | Cornerstone Advisors | |
| 38 | Glenmede | |
| 39 | PFM Asset Management | U.S. Bank subsidiary |
| 40 | TIAA (Nuveen) | |
| 41 | StepStone Group | |
| 42 | Hamilton Lane | Leading private market OCIO |
| 43 | Graystone Consulting | Morgan Stanley boutique brand |
| 44 | Perella Weinberg Partners | |
| 45 | Edgehill Endowment Partners | |
| 46 | Global Endowment Management (GEM) | |
| 47 | OCIO Alternative Investments | |
| 48 | Slocum | Now part of Pavilion/Mercer |
| 49 | Spider Management Company | |
| 50 | Rockefeller Capital Management | |

Also monitor: **eCIO** (nonprofit-only RIA, standing behavioral flag active — see Layer 1)

### Tier B — Leading institutional & specialized OCIOs (#11–30)
Specialize in nonprofit (E&F), healthcare, or defined benefit. High Priority signals only.

| # | Firm | Notes |
|---|---|---|
| 11 | Bank of America | Ranked #1 Non-Profit OCIO AUM 2026 |
| 12 | Cambridge Associates | |
| 13 | Verus Investments | |
| 14 | NEPC | New England Pension Consultants |
| 15 | Wilshire Advisors | |
| 16 | Strategic Investment Group | |
| 17 | Callan | |
| 18 | Northern Trust | |
| 19 | WTW | Willis Towers Watson |
| 20 | Commonfund | Heavy endowment focus |
| 21 | Hirtle Callaghan & Co. | Pioneer of the OCIO model |
| 22 | Brown Brothers Harriman | |
| 23 | UBS Institutional | |
| 24 | Vanguard Institutional | |
| 25 | Cerity Partners | 2025 Asset Management award winner |
| 26 | Alan Biller and Associates | |
| 27 | Angeles Investment Advisors | |
| 28 | HighVista Strategies | |
| 29 | Hall Capital Partners | |
| 30 | TIFF Investment Management | Investment Fund for Foundations |

### Tier C — Global heavyweights ("Big 10", #1–10)
Managing >$100B in discretionary OCIO assets. High Priority signals only — moves slowly but holds outsized market influence.

| # | Firm | AUM / Notes |
|---|---|---|
| 1 | Mercer | ~$670B AUM |
| 2 | Goldman Sachs Asset Management | ~$410B AUM |
| 3 | BlackRock | ~$372B AUM |
| 4 | Russell Investments | ~$355B AUM |
| 5 | Morgan Stanley Institutional | Ranked #1 U.S. market presence 2026 |
| 6 | Aon | Global advisory and pension mandates |
| 7 | J.P. Morgan Asset & Wealth Management | |
| 8 | SEI Institutional Group | |
| 9 | CAPTRUST | Rapidly climbing via aggressive acquisitions |
| 10 | State Street Global Advisors | |

### Hawaii local competitors (Layer 2 — unchanged)
Three firms competing for institutional clients in Farther's home market. Full weekly sweep.

| Firm | Local brand | Monitor for |
|---|---|---|
| **Morgan Stanley** | Hawaii Planning Group | Forbes/Barron's "Best-in-State" promotions · LinkedIn award posts · Financial Wellness content · New Hawaii hires |
| **UBS** | Hawaii Ascendant Wealth Consultants | Global macro thought leadership · "Start the Conversation" form changes · LinkedIn Ad Library Hawaii ads · Advisor team moves |
| **Mariner Wealth Advisors** | — | "Reset" podcast series · Tax-planning guides · Brand theme campaigns · New Hawaii hires or RFP activity |

### Key Hawaii signals to watch
- **Switch signal**: New hire announcements — Hawaii advisors move in teams and target existing ICP lists immediately
- **RFP keywords**: "New Endowment Partnership" · "Board Governance Workshop" · "Institutional RFP Hawaii"
- **Ad transparency**: LinkedIn Ad Library — weekly check for Hawaii-only sponsored content

---

## Profiles
Each competitor has a profile in `profiles/[firm-slug]-profile.md`.
Load only the profile(s) for competitors being swept this session — do not load all 50.
After each sweep: update the relevant profile's intelligence timeline, what Wren knows, and open threads.
Blank template: `profiles/_template.md` — copy and rename for new competitors.

Priority profiles built: `ecio-profile.md` · `bank-of-america-profile.md` · `captrust-profile.md`
Remaining 47 firms: create profile from template on first sweep.

## Skills
Load in order: `honesty.md` → `weekly-sweep.md` → `signal-classification.md` → `alert-writer.md` → `behavioral-pattern-analysis.md`

## Output
Slack: concise bullets per section and layer, flag tier, source.
HTML report: full findings organized by layer then section.
Save as: `outputs/YYYY-MM-DD-weekly.html`

## Rules
- Read `honesty.md` before every output.
- Three tiers only: Confirmed (cited source) · Inferred (named data) · Speculative (flagged hypothesis).
- Never present self-reported data as independently verified.
- Coverage gaps to note: LinkedIn rate limits · ADV annual cadence · gated content not fully accessible · LinkedIn Ad Library requires manual check.

---

## Memory maintenance
After every sweep — successful or failed — update memory.md before closing the session.
- Successful run: update Last run, What I currently know, resolve any open threads
- Failed run: log the error in Failures and fixes, apply the fix, update the relevant skill file so it does not happen again
- Never hand the memory file back to a human to write — Wren owns this file
