# memory.md — Wren · Stealth Competitor Intelligence Agent

> This file is written and maintained by Wren, not by humans.
> Detailed competitor findings live in profiles/ — not here.
> This file tracks operational state only: last run, open threads, decisions.
> Cap: 40 lines. Prune before adding. Archive entries older than 30 days.

---

## Last run
Date: 2026-06-06
Competitors swept: Full 12-channel field sweep (50 firms) + eCIO Layer 1 + first Hawaii baseline
Signals processed: 27 · High: 6 · Medium: 9 · Low: 8 · Discarded: 4
Report generated: outputs/2026-06-06-wren-weekly.html
Status: Successful · Behavioral flags active: 2 (FLAG-001, FLAG-002 upgraded) · Watching: WATCH-001/002/003

---

## Open threads (cross-competitor)
- [ ] WATCH-003: watch for a 4th E&F-relevant acquisition by ~Sept 2026 (CAPTRUST/Cerity/Fiducient wave)
- [ ] Retrieve Chestnut Solutions Institute 2025 Global OCIO Survey — verify BofA #1 nonprofit / $79.2B (currently Inferred)
- [ ] CAPTRUST Carnegie ($7.5B) — confirm or drop (still "in talks" only)
- [ ] eCIO: capture primary LinkedIn posts to confirm/drop Tucson IDA + Perinatal Foundation client leads
- [ ] Manual IAPD ADV pull for top Tier A firms (web fetch can't parse PDF brochures) — incl. eCIO CRD# 301432
- [ ] Supervisor decision: reclassify Mariner as national/watch-only for Hawaii (no HI office)
- [ ] BofA FLAG-002 Test 2: watch for OCIO 2.0 framed as a required standard (would deepen flag)

---

## Decisions made
- 2026-06-06: FLAG-002 (BofA) upgraded Watching → Active — consolidation article confirmed (single-OCIO "best practice")
- 2026-06-06: WATCH-003 created — industry-wide E&F/OCIO consolidation wave across 3 Tier A firms in ~6 weeks
- 2026-06-06: First Hawaii baseline complete (MS, UBS confirmed; Mariner has no HI office) — resolves prior open thread
- 2026-06-06: First BofA + CAPTRUST sweeps complete — resolves prior open threads
- 2026-06-06: 6 new profiles created (Cerity, Fiducient, Glenmede, MS-Hawaii, UBS-Hawaii, Mariner)
- 2026-06-06: Corrected NACUBO Mercer speaker (Cori Trautvetter, not Texas Hemmaplardh); Mariner–State Street = tech partnership not acquisition

---

## Failures and fixes
> Wren logs errors here. When something breaks: document it, fix it, update the relevant skill.

- 2026-06-06: One research agent died mid-sweep on a transient API billing error ("Credit balance too low"), returning zero output for Channels 1/2/6/9. Fix: relaunched a single scoped agent for those channels — recovered cleanly. No skill change needed; if recurring, split fan-out into smaller batches.

---

## Instructions to Wren
- After every sweep: update Last run, resolve open threads, log decisions
- After every failure: log error + fix here, then update the relevant skill file
- Detailed findings go in profiles/ not here — keep this file lean
- Never hand this file to a human to write — Wren owns it
