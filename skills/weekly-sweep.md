# weekly-sweep.md — Wren Signal-First Sweep Protocol

> This is how Wren runs her weekly sweep.
> Not: "visit each competitor and see what's new."
> Yes: "scan the market for these signals, identify who fired them."
> If nothing fires, say so. Don't fill the report with check-ins.

---

## The model

Wren does not visit 50 websites.
Wren listens to 12 signal channels.
When a signal fires, it lights up a profile.
If no profile exists yet for that firm, Wren creates one from _template.md.
If nothing fires on a given channel, that channel gets one line: "No activity detected."

The report reflects what actually happened in the market this week —
not a status update on what 50 firms are generally up to.

---

## The 12 signal channels

Run these queries every sweep. Each channel has a purpose and a set of search strings.

### Channel 1 — Client wins
**Purpose:** Who just announced a new nonprofit client relationship?
**Queries:**
- `"new client" OR "new partnership" nonprofit endowment foundation investment advisor 2026`
- `"pleased to welcome" OR "proud to serve" nonprofit endowment foundation`
- `"investment committee" "new advisor" OR "selected" site:linkedin.com`

**Fires when:** Any of the 50 firms named in a nonprofit client announcement
**Profile action:** Add to intelligence timeline · Update "What Wren knows" · Flag as High Priority

---

### Channel 2 — RFP activity
**Purpose:** Who is responding to or publishing nonprofit investment RFPs?
**Queries:**
- `"request for proposal" "investment advisor" OR "OCIO" nonprofit endowment 2026`
- `"RFP" "investment management" foundation endowment site:gov OR site:org`
- SAM.gov: search each Tier A firm name + "investment advisory"

**Fires when:** A public RFP names or is responded to by any of the 50 firms
**Profile action:** Log RFP details · Flag as High Priority

---

### Channel 3 — Acquisitions and mergers
**Purpose:** Who just acquired or merged with a firm in our competitive space?
**Queries:**
- `[firm name] acquires OR "acquisition" OR "merger" OR "joins" 2026`
- `"RIA acquisition" nonprofit advisory 2026`
- `CAPTRUST OR Mercer OR Goldman OR BlackRock acquires 2026`

**Fires when:** Any of the 50 firms announces an acquisition of a nonprofit-adjacent RIA
**Profile action:** High Priority · Update profile immediately · Check if acquired firm serves nonprofits

---

### Channel 4 — Thought leadership on nonprofit investing
**Purpose:** Who just published content targeting nonprofit boards or investment committees?
**Queries:**
- `site:[competitor domain] endowment OR foundation OR nonprofit 2026`
- `"investment committee" "board" "endowment" "spending policy" OR "UPMIFA" site:linkedin.com 2026`
- `"nonprofit investment" webinar OR guide OR whitepaper 2026`

**Fires when:** New content published by any of the 50 firms targeting nonprofit audiences
**Gated content rule:** Any gated asset (requires name/email/org) — always flag for behavioral-pattern-analysis.md regardless of priority tier

---

### Channel 5 — Award and ranking announcements
**Purpose:** Who just got ranked, awarded, or recognized in nonprofit advisory?
**Queries:**
- `"best nonprofit investment advisor" OR "top OCIO" OR "endowment manager" award 2026`
- `Forbes OR Barron's OR "Pensions & Investments" OR NACUBO ranking advisor 2026`
- `"Best-in-State" OR "top advisor" Hawaii 2026`

**Fires when:** Any of the 50 firms wins a nonprofit-relevant award or ranking
**Profile action:** Medium Priority · Note in intelligence timeline

---

### Channel 6 — Key hires and departures
**Purpose:** Who just hired or lost someone with nonprofit expertise?
**Queries:**
- `"joins" OR "named" OR "appointed" "nonprofit" OR "endowment" OR "foundation" advisor 2026 site:linkedin.com`
- `"pleased to announce" "endowment" OR "foundation" OR "OCIO" site:linkedin.com`
- Hawaii: `"advisor" "Hawaii" "joins" OR "named" site:linkedin.com 2026`

**Fires when:** A director-level or above hire/departure with nonprofit focus at any of the 50 firms
**Hawaii rule:** Any advisor move in Hawaii — always High Priority regardless of firm tier

---

### Channel 7 — Conference and event presence
**Purpose:** Who is showing up at nonprofit sector conferences?
**Queries:**
- `NACUBO OR "Council on Foundations" OR AFP OR "Exponent Philanthropy" sponsor OR speaker 2026`
- `"board governance" OR "investment committee" OR "endowment" conference sponsor 2026`
- LinkedIn Ad Library: check top 5 Tier A firms for nonprofit-targeted sponsored content

**Fires when:** Any of the 50 firms sponsors or speaks at a Tier A nonprofit conference
**Profile action:** Medium Priority · Note conference, role (sponsor/speaker/exhibitor), topic if known

---

### Channel 8 — Market-shaping content
**Purpose:** Who is trying to rewrite how nonprofits evaluate or hire advisors?
**Queries:**
- `"how to choose" OR "how to hire" OR "how to evaluate" "investment advisor" nonprofit 2026`
- `"skip the RFP" OR "do you need an RFP" OR "alternatives to RFP" nonprofit advisor`
- `"investment policy statement" guide download nonprofit 2026`

**Fires when:** Any content coaching nonprofits on advisor selection in ways that structurally favor the publisher
**Always flag for behavioral-pattern-analysis.md**

---

### Channel 9 — Regulatory and ADV changes
**Purpose:** Who just filed a material ADV change?
**Queries:**
- SEC EDGAR: check ADV amendments for top 10 Tier A firms each sweep
- Flag: charitable org client count change 20%+, new OCIO service type added, minimum account size dropped, new state registrations

**Fires when:** Material change detected in ADV
**Profile action:** High Priority if client count jumps · Medium if fee or service change

---

### Channel 10 — Campaign and messaging signals
**Purpose:** Are any rivals running a coordinated outbound campaign targeting nonprofit audiences?
A single article is Channel 4. A coordinated campaign — sustained theme across multiple surfaces
within 60 days — is this channel. The question is not "did they publish content" but
"are they trying to own a narrative right now?"

**Queries:**
- `site:[competitor domain] "newsletter" OR "webinar" OR "register" OR "upcoming event" nonprofit 2026`
- `"[firm name]" nonprofit webinar OR "virtual event" OR "roundtable" 2026`
- `"[firm name]" newsletter endowment OR foundation OR "investment committee" 2026`
- Webinar landing pages: check top 10 Tier A firms for active registrations or recorded replays

<!--
LINKEDIN SPONSORED CONTENT — PENDING APIFY ENTERPRISE ACCESS
When Apify is available, add:
- LinkedIn Ad Library: search each Tier A firm for active nonprofit-targeted sponsored posts
- Flag: ad copy themes, CTA type (gated download / event registration / direct contact),
  estimated run duration, targeting signals if visible
Status: waiting on confirmation of Farther enterprise Apify account
Do not activate until confirmed.
-->

**Fires when:** Any of the 50 firms has 2+ active campaign surfaces (webinar + newsletter,
email capture + content series, etc.) running a shared nonprofit theme within a 60-day window
**Single surface:** Log in profile, do not fire — route to Channel 4 instead
**Coordinated campaign:** High Priority · Always flag for behavioral-pattern-analysis.md
**Profile action:** Document surfaces observed, theme, estimated start date, CTA type (gated/ungated/event)

---

### Channel 11 — Behavioral pattern cross-check
**Purpose:** Do any new signals connect to known standing flags?
**Action:** After running Channels 1–10, cross-reference all fired signals against behavioral flags in active profiles. Channel 10 campaign signals are especially likely to connect — a coordinated campaign is often the visible surface of a deeper strategic pattern.
- eCIO: does any new signal fit the RFP funnel playbook?
- Any other firm: does a new pattern emerge across 2+ signals?

**Fires when:** New signal matches a standing flag pattern, or a new pattern becomes visible across signals
**Always flag for behavioral-pattern-analysis.md**

---

### Channel 12 — Earned media and news
**Purpose:** Who is in the news for nonprofit advisory activity?
**Queries:**
- `[firm name] nonprofit OR endowment OR foundation 2026` — run for all Tier A firms
- `OCIO nonprofit news 2026`
- `"outsourced CIO" foundation endowment news 2026`

**Fires when:** Any of the 50 firms appears in trade press or general news for nonprofit activity
**Sources:** InvestmentNews · AdvisorHub · Pensions & Investments · Barron's · Institutional Investor

---

## Sweep output rules

### If signals fire:
- Report only firms where something actually happened
- One finding card per signal (use alert-writer.md format)
- Load the relevant profile, update it, note it in the report

### If no signals fire on a channel:
- One line only: `Channel [N] — [name]: No activity detected this sweep.`
- Do not fabricate findings to fill the report

### Report structure:
```
🪶 Wren · Weekly Brief · [DATE]

SIGNALS FIRED THIS WEEK: [N] across [N] firms

[Firm name] — [signal type] — [priority]
[Finding card]

[Firm name] — [signal type] — [priority]
[Finding card]

CHANNELS WITH NO ACTIVITY: [list]
PROFILES UPDATED: [list]
PROFILES CREATED: [list — new firms encountered]
Next sweep: [date]
```

---

## What this is not
- Not a status report on what 50 firms are generally doing
- Not "I checked CAPTRUST's website and nothing has changed"
- Not padding with low-signal observations to make the report look full
- Not a check-in. A wire tap.

If nothing fired this week, the report is short. That is a good outcome.
A quiet week is intelligence too.
