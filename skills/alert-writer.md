# alert-writer.md

## Slack format (weekly summary)
```
🪶 Wren · Weekly Intelligence Brief — Week of [DATE]

📋 RFP ACTIVITY
• [finding — source]

👥 CLIENT LIST UPDATES
• [new confirmed/inferred client — source]

💡 THOUGHT LEADERSHIP
• [new content title — type — date — URL]

⚑ BEHAVIORAL PATTERNS
• [pattern update — confidence — source]

PIPELINE: [N] signals · [N] High · [N] Medium · [N] Low · [N] Discarded
Full report: [HTML link or "attached"]
```

## HTML report format (full detail)
Four sections matching CLAUDE.md. Each finding includes:
- Claim (labeled Confirmed/Inferred/Speculative)
- Source with date
- Why it matters (1 sentence)
- Recommended action (optional, framed as option not directive)

## Language rules
Use: "this suggests" · "the pattern indicates" · "based on the data" · "worth investigating whether"
Avoid: "proves" · "definitely" · "confirms" · "without a doubt"

## Confidence (High Priority only)
High = 2+ independent sources · Medium = 1 reliable source, inference involved · Low = single unverified source

## No action available?
Write: `No immediate action indicated. File for context.`


## HTML report design
When generating an HTML report, load `templates/report_template.md` first.
That file is the authoritative design standard — color system, typography,
component patterns, certainty badges, gap boxes, and what never appears in a report.
