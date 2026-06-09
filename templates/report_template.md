# report_template.md — Wren HTML Report Visual Standard

## Purpose
This is the authoritative visual standard for all Wren and Farther Institutional
intelligence reports. Load this file whenever alert-writer.md instructs you to
generate an HTML report. Reproduce the CSS and structure below exactly — do not
improvise or substitute fonts, colors, or component patterns.

---

## Design principles
- **Editorial, not dashboard.** Reports are read, not scanned. Typography and
  whitespace carry as much weight as data.
- **Honest by design.** Every finding carries a visible certainty badge. The
  reader never has to guess how confident a claim is.
- **Balanced by structure.** Every competitor gets equal section space regardless
  of finding volume. Thin sections get a baseline gap box — they never disappear.
- **Print-ready.** `-webkit-print-color-adjust: exact` ensures clean printing.

---

## Fonts
Always load both from Google Fonts in the `<head>`:
```html
<link href="https://fonts.googleapis.com/css2?family=Spectral:ital,wght@0,300;0,400;0,500;1,300&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
```

When writing HTML reports, copy the <head> skeleton from report_template.md verbatim. Do not reconstruct it from memory.

- **Spectral** (serif) — body text, finding descriptions, all prose
- **DM Mono** (monospace) — all labels, badges, metadata, source lines, stats bar


---

## Complete CSS — copy verbatim into every report

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
:root {
  --bg: #f5f4ef;
  --surface: #ffffff;
  --ink: #1c1c18;
  --ink-mid: #5a5a52;
  --ink-dim: #9a9a90;
  --rule: #ddddd4;
  --rule-dark: #b8b8ac;
  --wren: #3d6b4f;
  --wren-light: #edf4ef;
  --wren-mid: #c0d9c8;
  --alert-red: #8b2e2e;
  --alert-red-bg: #fdf2f2;
  --alert-red-rule: #e8c4c4;
  --amber: #7a5200;
  --amber-bg: #fdf8ee;
  --amber-rule: #e8d8a0;
  --blue: #1e3d6b;
  --blue-bg: #f0f4fb;
  --blue-rule: #b8ccec;
  --mono: 'DM Mono', monospace;
  --serif: 'Spectral', Georgia, serif;
}

html, body {
  background: var(--bg);
  color: var(--ink);
  font-family: var(--serif);
  font-size: 15px;
  line-height: 1.75;
}

.masthead {
  background: var(--ink);
  color: #f5f4ef;
  padding: 36px 56px 28px;
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  flex-wrap: wrap;
  gap: 16px;
}
.masthead-left .wren-name {
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--wren);
  margin-bottom: 6px;
}
.masthead-left h1 {
  font-size: 24px;
  font-weight: 300;
  font-style: italic;
  color: #f5f4ef;
  line-height: 1.2;
}
.masthead-right {
  text-align: right;
  font-family: var(--mono);
  font-size: 11px;
  color: #6a6a60;
  line-height: 1.9;
}

.stats-bar {
  background: #252520;
  padding: 10px 56px;
  display: flex;
  gap: 28px;
  flex-wrap: wrap;
  align-items: center;
  border-bottom: 1px solid #3a3a30;
}
.stat {
  font-family: var(--mono);
  font-size: 11px;
  color: #6a6a60;
  display: flex;
  align-items: center;
  gap: 6px;
}
.stat .n { color: #f5f4ef; font-size: 13px; font-weight: 500; }
.stat-div { width: 1px; height: 14px; background: #3a3a30; }

.wren-note {
  background: var(--wren-light);
  border-left: 3px solid var(--wren);
  padding: 14px 56px;
  font-size: 13px;
  color: var(--wren);
  font-family: var(--mono);
  display: flex;
  gap: 12px;
  align-items: flex-start;
}
.wren-note .label { font-weight: 500; white-space: nowrap; margin-top: 1px; }

.body { max-width: 860px; margin: 0 auto; padding: 44px 56px 80px; }

.layer { margin-bottom: 52px; }
.layer-header {
  display: flex;
  align-items: center;
  gap: 14px;
  margin-bottom: 6px;
}
.layer-tag {
  font-family: var(--mono);
  font-size: 10px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 3px 8px;
  border-radius: 3px;
}
.tag-national { background: var(--ink); color: #f5f4ef; }
.tag-hawaii { background: var(--wren); color: #f5f4ef; }
.layer-name { font-size: 20px; font-weight: 400; color: var(--ink); }
.layer-sub {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--ink-dim);
  margin-bottom: 20px;
  padding-left: 2px;
}
.layer-rule { height: 1px; background: var(--ink); margin-bottom: 24px; }

.competitor { margin-bottom: 36px; }
.comp-header {
  display: flex;
  align-items: baseline;
  gap: 10px;
  margin-bottom: 12px;
  padding-bottom: 8px;
  border-bottom: 1px solid var(--rule-dark);
}
.comp-name { font-size: 16px; font-weight: 500; color: var(--ink); }
.comp-aka { font-family: var(--mono); font-size: 11px; color: var(--ink-dim); }
.comp-count {
  margin-left: auto;
  font-family: var(--mono);
  font-size: 11px;
  color: var(--ink-dim);
  background: var(--bg);
  border: 1px solid var(--rule);
  padding: 2px 8px;
  border-radius: 3px;
}

.finding {
  padding: 14px 0;
  border-bottom: 1px solid var(--rule);
  display: grid;
  grid-template-columns: 88px 1fr;
  gap: 16px;
}
.finding:last-child { border-bottom: none; }
.finding-meta { padding-top: 2px; }
.cert-badge {
  font-family: var(--mono);
  font-size: 9px;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  padding: 3px 6px;
  border-radius: 3px;
  display: inline-block;
  margin-bottom: 6px;
  border: 1px solid transparent;
}
.c-confirmed { background: #edf4ef; color: #2a5c3a; border-color: #b0d4bc; }
.c-inferred  { background: var(--amber-bg); color: var(--amber); border-color: var(--amber-rule); }
.c-speculative { background: var(--blue-bg); color: var(--blue); border-color: var(--blue-rule); }
.c-flag { background: var(--alert-red-bg); color: var(--alert-red); border-color: var(--alert-red-rule); }
.c-gap { background: #f5f4ef; color: var(--ink-dim); border-color: var(--rule); }

.finding-priority {
  font-family: var(--mono);
  font-size: 9px;
  letter-spacing: 0.06em;
  color: var(--ink-dim);
  text-transform: uppercase;
}
.p-high { color: var(--alert-red); }
.p-medium { color: var(--amber); }
.p-low { color: var(--ink-dim); }

.finding-title {
  font-size: 14px;
  font-weight: 500;
  color: var(--ink);
  margin-bottom: 4px;
  line-height: 1.4;
}
.finding-desc {
  font-size: 13px;
  color: var(--ink-mid);
  line-height: 1.65;
  margin-bottom: 6px;
}
.finding-desc em { font-style: italic; color: var(--ink); }
.finding-source {
  font-family: var(--mono);
  font-size: 10px;
  color: var(--ink-dim);
}
.finding-source a { color: var(--blue); text-decoration: none; }
.finding-source a:hover { text-decoration: underline; }
.finding-action {
  margin-top: 8px;
  font-size: 12px;
  color: var(--amber);
  font-family: var(--mono);
  padding: 6px 10px;
  background: var(--amber-bg);
  border: 1px solid var(--amber-rule);
  border-radius: 3px;
  line-height: 1.5;
}
.finding-action strong {
  font-size: 9px;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  display: block;
  margin-bottom: 2px;
}

.gap-box {
  background: var(--bg);
  border: 1px dashed var(--rule-dark);
  border-radius: 6px;
  padding: 16px 20px;
  margin-bottom: 12px;
  font-family: var(--mono);
  font-size: 12px;
  color: var(--ink-dim);
  line-height: 1.7;
}
.gap-box strong {
  color: var(--ink-mid);
  display: block;
  margin-bottom: 4px;
  font-size: 11px;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}

.section-label {
  font-family: var(--mono);
  font-size: 10px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--ink-dim);
  margin: 28px 0 12px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.section-label::after {
  content: '';
  flex: 1;
  height: 1px;
  background: var(--rule);
}

.slack-preview {
  background: #1a1d21;
  border-radius: 8px;
  padding: 24px 28px;
  margin-bottom: 48px;
  font-family: var(--mono);
  font-size: 12px;
  color: #d1d2d3;
  line-height: 1.8;
}
.slack-preview .slack-header {
  font-size: 11px;
  color: #6a6a70;
  margin-bottom: 16px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.slack-channel { color: #4a9eda; }
.slack-bot { color: #7c8b9a; }
.slack-preview .bold { color: #ffffff; font-weight: 500; }
.slack-preview .green { color: #4CAF7A; }
.slack-preview .amber { color: #e8a44a; }
.slack-preview .red { color: #e07070; }
.slack-preview .dim { color: #6a6a70; }
.slack-divider { border: none; border-top: 1px solid #2e3238; margin: 12px 0; }

footer {
  background: var(--ink);
  color: #5a5a52;
  padding: 20px 56px;
  font-family: var(--mono);
  font-size: 11px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 8px;
}
footer span { color: var(--wren); }
```

---

## HTML page skeleton — copy verbatim, fill in dynamic values

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Wren · Weekly Intelligence Brief · [DATE]</title>
<link href="https://fonts.googleapis.com/css2?family=Spectral:ital,wght@0,300;0,400;0,500;1,300&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  /* paste full CSS above here */
</style>
</head>
<body>

<div class="masthead">
  <div class="masthead-left">
    <div class="wren-name">Wren · Stealth Competitor Intelligence</div>
    <h1>Weekly Intelligence Brief</h1>
  </div>
  <div class="masthead-right">
    Week of [DATE RANGE]<br>
    Farther Institutional · Internal use only<br>
    Honesty standard: Confirmed / Inferred / Speculative
  </div>
</div>

<div class="stats-bar">
  <div class="stat"><span class="n">[N]</span> signals processed</div>
  <div class="stat-div"></div>
  <div class="stat"><span class="n">[N]</span> High</div>
  <div class="stat"><span class="n">[N]</span> Medium</div>
  <div class="stat"><span class="n">[N]</span> Low</div>
  <div class="stat"><span class="n">[N]</span> Discarded</div>
  <div class="stat-div"></div>
  <div class="stat"><span class="n">[N]</span> competitors monitored</div>
  <div class="stat"><span class="n">[N]</span> behavioral flags active</div>
</div>

<div class="wren-note">
  <div class="label">Wren —</div>
  <div>[Transparency note about data quality, first sweeps, or confidence
  asymmetry this week. Never skip this block.]</div>
</div>

<div class="body">

  <!-- SLACK PREVIEW -->
  <div class="section-label">Slack summary — delivered to #institutional-intel</div>
  <div class="slack-preview">
    <div class="slack-header">
      <span class="slack-channel">#institutional-intel</span>
      <span class="slack-bot">Wren · Today at 8:02 AM HST</span>
    </div>
    <div><span class="bold">🪶 Wren · Weekly Brief · [DATE]</span></div>
    <hr class="slack-divider">
    <!-- One block per competitor:
    <div><span class="bold">[Competitor name]</span></div>
    <div><span class="red">🔴 High</span> — [finding] <span class="dim">[source]</span></div>
    <div><span class="amber">🟡 Medium</span> — [finding] <span class="dim">[source]</span></div>
    <div><span class="green">🟢 Low</span> — [finding]</div>
    <hr class="slack-divider">
    -->
    <div><span class="dim">Full report attached · Next sweep: [DATE] · Questions: mention @Wren</span></div>
  </div>

  <!-- LAYER: NATIONAL -->
  <div class="layer">
    <div class="layer-header">
      <div class="layer-tag tag-national">National</div>
      <div class="layer-name">[Competitor]</div>
    </div>
    <div class="layer-sub">[domain · location · CRD# · descriptor]</div>
    <div class="layer-rule"></div>
    <div class="section-label">[section name]</div>
    <div class="competitor">
      <div class="finding">
        <div class="finding-meta">
          <div class="cert-badge c-confirmed">Confirmed</div>
          <div class="finding-priority p-high">High</div>
        </div>
        <div class="finding-body">
          <div class="finding-title">[One-line plain-English summary]</div>
          <div class="finding-desc">[2–4 sentences. Neutral language.]</div>
          <div class="finding-source">Source: <a href="[URL]">[domain/path]</a> · retrieved [date]</div>
          <div class="finding-action">
            <strong>Worth considering</strong>
            [1–2 sentence option, framed as a question not a directive]
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- LAYER: HAWAII -->
  <div class="layer">
    <div class="layer-header">
      <div class="layer-tag tag-hawaii">Hawaii</div>
      <div class="layer-name">Local Competitors</div>
    </div>
    <div class="layer-sub">[competitor names · sweep status]</div>
    <div class="layer-rule"></div>
    <div class="competitor">
      <div class="comp-header">
        <div class="comp-name">[Firm name]</div>
        <div class="comp-aka">[Local brand name]</div>
        <div class="comp-count">[N] findings · first sweep</div>
      </div>
      <!-- Gap box if first sweep or thin data: -->
      <div class="gap-box">
        <strong>Baseline note</strong>
        [Explain why findings are thin. Never silently omit a competitor.]
      </div>
      <!-- findings here -->
    </div>
  </div>

</div>

<footer>
  <div><span>Wren</span> · Stealth Competitor Intelligence Agent · Farther Institutional</div>
  <div>Honesty standard applied throughout · Read honesty.md before acting on findings</div>
  <div>Generated [DATE] · Next sweep: [NEXT DATE]</div>
</footer>

</body>
</html>
```

---

## Certainty badges — use exactly these classes

```html
<div class="cert-badge c-confirmed">Confirmed</div>
<div class="cert-badge c-inferred">Inferred</div>
<div class="cert-badge c-speculative">Speculative</div>
<div class="cert-badge c-flag">⚑ Pattern</div>
<div class="cert-badge c-gap">Gap</div>
```

## Priority labels — always pair with cert badge

```html
<div class="finding-priority p-high">High</div>
<div class="finding-priority p-medium">Medium</div>
<div class="finding-priority p-low">Low</div>
```

## Layer tags — one per layer

```html
<div class="layer-tag tag-national">National</div>
<div class="layer-tag tag-hawaii">Hawaii</div>
```
Add new tags (e.g. `tag-west-coast`, `tag-southeast`) by extending the CSS
with the same pattern as `tag-hawaii`, using a new background color.

---

## What never appears in a report
- "proves" · "definitely" · "confirms that" · "without a doubt" · "clearly they are"
- A finding without a certainty badge
- A finding without a source citation
- A competitor with zero findings and no gap box
- Farther's own content as competitive intelligence
- Self-reported competitor data presented as independently verified

---

## File naming
```
wren/outputs/YYYY-MM-DD-wren-weekly.html       ← standard weekly
wren/outputs/YYYY-MM-DD-wren-hawaii.html       ← Hawaii layer only
wren/outputs/YYYY-MM-DD-wren-[competitor].html ← single competitor deep dive
```

---

## HTML delivery method

### Claude Code (primary — local file system)
Write the report directly to disk using the file naming convention above.

```
outputs/YYYY-MM-DD-wren-weekly.html
```

Claude Code has full write access to the `Wren/` folder. After generating the report HTML, write it to `outputs/` immediately. Do not display it in the chat — just confirm the file was written and the path.

The user opens the file in any browser to view the rendered report. It can then be shared, printed, or sent to the supervisor directly.

### Claude Project / web interface (fallback)
When running in a Claude Project without file write access, produce the HTML as a **Claude artifact** typed as `text/html`. This renders the report visually in the artifact panel and gives the user a download button.

Never output raw HTML as an inline code block — this produces unrendered markup the user cannot read or share.

### Converting chat findings to a report
If Wren has already produced findings in the chat and the user asks to convert them into a formatted report:
1. Take all findings from the current session
2. Apply the full CSS and HTML skeleton from this template
3. In Claude Code → write to `outputs/YYYY-MM-DD-wren-weekly.html`
4. In Claude Project → produce as artifact