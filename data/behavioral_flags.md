# behavioral_flags.md — Wren Standing Behavioral Patterns

> Wren reads this at the start of every sweep for Channel 11 (behavioral cross-check).
> Wren writes to this file when behavioral-pattern-analysis.md confirms a new pattern.
> Humans may review but should not overwrite confirmed entries.
> Last updated: 2026-06-06

---

## How Channel 11 uses this file

At the end of every sweep, after Channels 1–10 have run, Wren:
1. Reads all Active flags in this file
2. Cross-references every signal found this sweep against each flag's known playbook
3. If a new signal matches a standing pattern → escalates to High Priority and notes "consistent with standing flag"
4. If a new signal contradicts a standing pattern → notes "possible strategy shift" and escalates
5. If a new pattern is emerging across 2+ new signals → creates a new entry below as Watching

---

## Active Flags

### ⚑ FLAG-001 — eCIO RFP Funnel
**Firm:** eCIO (getecio.com)
**Status:** Active
**Confidence:** High
**Date confirmed:** 2026-06-05
**Pattern type:** Contradiction + Funnel + Market-shaping + Cross-channel

**The playbook — five confirmed steps:**
1. Nonprofit searches for RFP guidance → finds eCIO's free RFP template (gated — captures name, email, org)
2. Downloads template → encounters "Should You Issue an RFP?" content coaching prospects to skip formal process
3. eCIO frames its own evaluation criteria inside the process guide (buyer conditioning)
4. Nonprofit submits RFP directly to eCIO via dedicated submission portal
5. Zero public RFPs found in SAM.gov — wins appear to come from private/informal processes

**Contradiction confirmed:** RFP submission portal live at same time as skip-the-RFP coaching content. Both actively promoted simultaneously.

**Primary sources:**
- getecio.com/submit-an-investment-management-request-for-proposal-rfp · retrieved Jun 2026
- getecio.com/resources/should-you-issue-an-rfp-to-select-your-next-investment-advisor · retrieved Jun 2026
- getecio.com/resource-center/rfp-resources · retrieved Jun 2026
- SAM.gov search — "eCIO investment advisory" — zero results · retrieved Jun 5, 2026

**What to check every sweep:**
- Any new LinkedIn post from eCIO — does it promote the RFP portal, skip-the-RFP content, or a new gated asset?
- Any new gated PDF or guide on getecio.com → document what the gate collects
- Any new RFP-related content → does it reinforce or contradict the dual-track strategy?
- SAM.gov → still zero results?

**New iterations logged:**
- 2026-06-06: Funnel fully re-confirmed from primary sources — no strategy shift. Gated template, skip-the-RFP coaching, embedded evaluation criteria, live submission portal, zero SAM.gov all intact. Two unverified LinkedIn client-win posts (Tucson IDA, Perinatal Foundation) observed as adjacent "publicize the win" behavior — not the funnel itself.
- 2026-06-05: Full five-step funnel confirmed and documented from primary sources · first sweep

---

### ⚑ FLAG-002 — BofA "OCIO 2.0" + Consolidation Displacement
**Firm:** Bank of America
**Status:** ACTIVE — upgraded from Watching 2026-06-06 (consolidation-article test met)
**Confidence:** Medium-High
**Date flagged:** 2026-06-05 · **Date confirmed Active:** 2026-06-06
**Pattern type:** Market-shaping (consolidate-to-the-largest-provider)

**The pattern — two coordinated pieces:**
1. April 7, 2026 press release introduces "OCIO 2.0" — service framed as going beyond investment management (governance advisory, spending policy design, leadership development, fundraising strategy). Sells the expanded-capability vision.
2. Companion article "Should Nonprofits Consolidate Outsourced CIO Providers?" RETRIEVED this sweep — explicitly advises nonprofits to reduce to a SINGLE OCIO: "choosing a single OCIO provider remains a best practice… a unified OCIO gives you clarity, control and cohesion," warning that splitting endowments across providers leaves "no one… responsible for stewarding the entire portfolio" (Bernard Reidy, BofA Private Bank).

**Upgrade test result:**
- Test 1 (advises reducing # of advisors): MET — explicit single-OCIO "best practice" recommendation.
- Test 2 (frames OCIO 2.0 as a required new standard): NOT met within the article (no OCIO 2.0 reference there; that framing lives in the release).
- One of two met → upgraded to Active. The two pieces together form a coordinated consolidate-to-the-largest-provider narrative that structurally favors full-service mega-institutions (BofA) over boutiques (Farther).

**Primary sources:**
- privatebank.bankofamerica.com/articles/should-nonprofits-consolidate-ocio-providers.html (undated) · retrieved 2026-06-06
- newsroom.bankofamerica.com — "OCIO 2.0" release · Apr 7, 2026 · retrieved 2026-06-06

**What to check every sweep:**
- New "consolidation" / "single OCIO" content, or OCIO 2.0 framed as a required standard (would satisfy Test 2)
- Any nonprofit board-facing campaign reinforcing the consolidation theme
- William Jarvis (BofA) NACUBO Endowment Leadership Series appearance = same multi-channel push

**Evidence gaps:** Consolidation article carries no visible date. Chestnut Solutions Institute survey (basis of the "#1 nonprofit OCIO, $79.2B" claim) not directly retrieved — treat ranking as Inferred.

**New iterations logged:**
- 2026-06-06: Upgraded Watching → Active. Consolidation article confirmed. Jarvis NACUBO presence noted as reinforcing channel.

---

## Watching (Potential Patterns — Not Yet Confirmed)

### WATCH-001 — CAPTRUST acquisition pattern
**Firm:** CAPTRUST
**Date flagged:** 2026-06-05 · **Updated:** 2026-06-06
**Observation:** Stillwater Capital Advisors ($1.25B, explicitly serves endowments & foundations) CONFIRMED closed May 14, 2026. Carnegie ($7.5B) remains "in talks" only (Citywire Feb 2) — unconfirmed, absent from CAPTRUST's official news page. The pattern still suggests systematic absorption of boutique nonprofit advisory firms.
**Escalate to Active if:** Carnegie acquisition confirmed, or a third nonprofit-specialist firm acquired within 12 months.

### WATCH-002 — Cerity Partners rapid expansion
**Firm:** Cerity Partners (absorbed Verus Investments)
**Date flagged:** 2026-06-05 · **Updated:** 2026-06-06
**Observation:** Verus merger CONFIRMED closed March 31, 2026 (~$1.2T institutional AUA; Verus serves nonprofits 40+ yrs). The "explicit nonprofit OCIO service line" escalation criterion is now arguably met via the Verus arm. PE-backed (Genstar). Hold at Watching pending one more confirming signal.
**Escalate to Active if:** Another institutional acquisition announced within 6 months (now mid-2026 onward), or the Verus nonprofit-OCIO line is confirmed as actively marketed under the Cerity brand.

### WATCH-003 — Industry-wide E&F / OCIO consolidation wave
**Firms:** CAPTRUST · Cerity Partners · Fiducient (Wealthspire)
**Date flagged:** 2026-06-06
**Observation:** Three Tier A firms expanded endowment/foundation capability via M&A within ~6 weeks — CAPTRUST/Stillwater (May 14), Cerity/Verus (closed Mar 31), Fiducient-Wealthspire/Sellwood (announced Apr 22, with Axia Apr 7). The pattern indicates well-capitalized competitors are racing to consolidate boutique E&F advisory scale — the exact segment Farther Institutional serves. Pairs thematically with BofA's "consolidate to one OCIO" messaging (FLAG-002): the market is being told both that bigger/consolidated is better AND being rolled up to make it so.
**Escalate to Active if:** A fourth E&F-relevant acquisition by any competitor lands within the quarter (by ~Sept 2026), or a competitor explicitly markets the consolidation as a buyer benefit.

---

## Resolved Flags
> Patterns that have been confirmed as ended, reversed, or no longer active.

None yet.

---

## Instructions to Wren
- Read this file at the start of every sweep before running Channel 11
- After Channel 11 runs: update "New iterations logged" for any active flag that fired this sweep
- When behavioral-pattern-analysis.md confirms a new pattern: add a new Active Flag entry
- When a Watching entry reaches Medium+ confidence: move it to Active Flags
- When a pattern resolves or reverses: move it to Resolved with a note
