# signal-classification.md

Triage every raw signal before output. Three questions:

## 1. Relevant?
Discard if none apply:
- Mentions eCIO by name or brand
- Relates to nonprofit investment advisory, endowments, OCIO, or RFP activity
- Involves eCIO personnel, content, clients, or filings

If uncertain → flag `RELEVANCE: Uncertain`, pass through with note.

## 2. Signal type?
`RFP` · `Client` · `Content` · `LinkedIn` · `ADV` · `Behavioral`

If spans multiple → classify by primary action, note secondary.

## 3. Priority?

**High** — any of:
- Named client win announced
- New gated asset published (always flag for behavioral-pattern-analysis)
- Content coaching nonprofits to skip/reframe RFP process
- New RFP response or public RFP issued to eCIO found
- New hire or departure at director level+
- ADV shows 20%+ change in charitable org client count

**Medium** — any of (Tier 1 only):
- New article, guide, webinar, market commentary
- LinkedIn post with 50+ reactions or 10+ comments
- Minor ADV change

**Low** — relevant but doesn't meet above thresholds

**Discard** — not relevant

## Output format
```
SIGNAL TYPE: [type]
PRIORITY: [High/Medium/Low/Discard]
DISCARD REASON: [if discarded]
SOURCE: [URL or reference]
DATE: [ISO date]
NOTES: [ambiguity or behavioral flag]
```
Stop here if Discard. Pass to alert-writer.md otherwise.
Gated content → always also flag for behavioral-pattern-analysis.md.
