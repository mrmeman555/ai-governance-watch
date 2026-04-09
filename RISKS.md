# Risk Register — This Repository

> **What this is:** A running list of risks to this repo's credibility, accuracy, and usefulness. Each risk has a current status and a mitigation (often linking to a [governance control](controls/repo-governance.md)). This is the risk register; the controls doc is the control narrative.
>
> **Last reviewed:** 2026-04-08

---

## RR-01 — Content Staleness

**Risk:** Events are moving at days-per-development speed. Claims written April 8 may be outdated by April 15. Framework gaps documented today may be addressed in the next revision cycle.

**Current status: HIGH.** The entire repo was written in a single week (April 8, 2026). Every finding reflects the landscape as of that date. Nothing has been revisited yet.

**Mitigation:** RC-06 (Stale Findings) requires "Last updated" dates and review when standards bodies publish updates. CHANGELOG tracks what changed and when. But the mitigation only works if reviews actually happen.

**Open question:** What's the review cadence? Currently undefined beyond "when a relevant update occurs."

---

## RR-02 — Source Concentration

**Risk:** The repo's two biggest claims — the harness governance gap and the shifted security baseline — rely heavily on Anthropic's own disclosures (system card, blog posts, Glasswing announcement). Anthropic has commercial incentives to frame Mythos as both capable and responsibly managed. The system card is self-reported, not independently audited.

**Current status: MEDIUM.** Some independent sources exist (CrowdStrike, CyberScoop, Fortune, Innovaiden, Simon Willison), but the core technical claims (benchmark numbers, alignment findings, exploit counts) all originate from Anthropic.

**Mitigation:** RC-10 (Selection Bias) requires including contradictory evidence. SOURCES.md logs all sources for transparency. But no control currently requires source diversity.

**Open question:** Are there independent reproductions of the benchmark claims? Has anyone outside Anthropic validated the system card findings?

---

## RR-03 — AI Hallucination in Content

**Risk:** This repo was written with AI assistance (Claude). AI models fabricate plausible details — section numbers, benchmark scores, dates, quotes, organizational names. A hallucinated detail in a governance analysis could mislead practitioners.

**Current status: MEDIUM.** RC-04 requires human review. The author reviewed all content before committing. SOURCES.md provides a verification path. But the volume of content produced in one session increases the risk that a fabricated detail slipped through.

**Mitigation:** RC-04 (Unreviewed AI Output), RC-01 (Unsourced Claims). Citation keys link every claim to a source. SOURCES.md "Corrections Found During Source Verification" section documents errors caught so far.

**Known corrections made:** PSPDFKit exit value ($800M claim corrected to $116M), ISO 42001 section numbering (8.2 vs 8.4), HITRUST 51 vs 44 controls distinction, WIRED/ZDNET Glasswing coverage (not verified).

---

## RR-04 — Single-Author Bias

**Risk:** All analysis reflects one practitioner's interpretation. No peer review, no editorial board, no second opinion. The thesis ("two gaps converge") may reflect the author's framing more than the evidence warrants.

**Current status: HIGH.** No external review has occurred. The author is a GRC practitioner, not a framework standards body member or academic researcher.

**Mitigation:** RC-05 (Fact/Opinion Blending) separates events from analysis. RC-10 (Selection Bias) requires including inconvenient evidence. The README disclaimer states this is independent research, not compliance advice. But structural bias (which events to cover, which gaps to highlight, which frameworks to track) is inherent in single-author work.

**Open question:** Would external review change the conclusions? Which claims are most vulnerable to confirmation bias?

---

## RR-05 — Unverified Sources

**Risk:** Some citation keys in SOURCES.md reference sources that couldn't be verified during initial research. Claims built on these sources may be wrong.

**Current status: MEDIUM.** SOURCES.md maintains a "Pending Sources" table tracking 6 unresified sources, including: WIRED and ZDNET Glasswing coverage (may not exist), Mexico AI incident (no URL found), the repo's own GitHub URL (may be private).

**Mitigation:** RC-03 (Link Rot) requires enough context to locate sources even if URLs break. Pending sources are clearly marked. But claims that depend on unverified sources should be flagged more prominently in the artifacts themselves.

---

## RR-06 — Framework Interpretation Error

**Risk:** Gap claims may misread the framework text. ISO 42001, NIST AI RMF, and SOC 2 TSC are complex documents. The author's interpretation of what a clause "should" require may not reflect how auditors, assessors, or the standards body itself would read it.

**Current status: MEDIUM.** Specific section references are provided (Clause 8.4, GOVERN 2.1, CC6.1, etc.) so readers can verify. But the author has not consulted the purchased ISO 42001 standard text directly — secondary sources were used for Annex numbering.

**Mitigation:** RC-09 (Completeness Gap) requires disclosing what was checked. SOURCES.md notes "Annex numbering should be verified against the purchased standard." But the gap between "reading about" and "reading" a standard is a real risk for a governance-focused repo.

**Open question:** Has the author read the full text of ISO 42001, or only secondary summaries?

---

## RR-07 — Dual-Use Concern

**Risk:** The repo publishes exploit cost data ($50-$2,000 per exploit), capability benchmarks (Cybench 100% pass@1, Firefox 84% exploitation), and detailed descriptions of model circumvention techniques (safety classifier bypass, /proc credential fishing). This information could inform threat actors' cost-benefit calculations.

**Current status: LOW.** All information comes from Anthropic's own public disclosures (system card, blog posts). The repo adds no novel attack information. It aggregates and contextualizes what's already public.

**Mitigation:** The repo does not disclose vulnerability details beyond what Anthropic published. Exploit techniques described in the alignment section are behavioral patterns, not executable code.

---

## RR-08 — Scope Creep

**Risk:** The repo starts as a governance tracker and drifts into general AI commentary, model comparisons, or advocacy for specific tools/vendors.

**Current status: LOW.** Current scope is tightly defined: harness ecosystem + Glasswing + framework impact. But the Glasswing event brief's alignment section is already at the edge of governance relevance — it's deeply technical model safety analysis that may not be directly actionable for a GRC audience.

**Mitigation:** README defines scope. Templates enforce structure for new entries. RC-09 requires scope disclosure. But no control currently gates whether new content belongs in the repo.

---

## RR-09 — Vendor Advocacy

**Risk:** The repo mentions specific products (Cranium, Managed Agents, OpenClaw, Claw Code) in ways that could be read as endorsements.

**Current status: LOW.** Products are mentioned as examples of the pattern, not recommendations. The harness-governance-gap.md mentions Cranium as "one of the first products addressing this gap" — which is descriptive, not prescriptive.

**Mitigation:** RC-05 (Fact/Opinion Blending) applies. Product mentions should describe what the product does, not whether the reader should buy it.

---

## RR-10 — Temporal Compression Bias

**Risk:** The entire repo was built in one session on one day. The "10-week timeline" narrative was constructed retrospectively, and the analysis reflects a single moment's understanding. First impressions of the system card may differ from conclusions after deeper analysis.

**Current status: HIGH.** No cooling-off period has occurred. The Glasswing system card was published April 7; the repo's analysis was written April 8. The alignment assessment section was integrated from a single read of the 244-page PDF.

**Mitigation:** CHANGELOG provides a full audit trail of when content was added. The "Last updated" dates make the temporal compression visible. But the risk is in the analysis itself — first-read interpretations of a 244-page document may miss nuance.

**Open question:** After a second read of the system card, would the emphasis change? Are there findings that were underweighted or overweighted?

---

## RR-11 — Overstatement of Gaps

**Risk:** Framework gap claims may be stronger than warranted. SOC 2, ISO 42001, and NIST AI RMF are deliberately broad — their flexibility may already cover harness-level risks under existing language, even without explicit mention. Auditors and assessors may disagree that a "gap" exists.

**Current status: MEDIUM.** The repo acknowledges some framework flexibility (e.g., SOC 2 TSC's broad "Security" criteria). But phrases like "frameworks don't address the harness" could be read as claiming a deficiency when it may be a matter of interpretation.

**Mitigation:** Framework docs use "Gap/finding" language rather than "Deficiency." The disclaimer states these are the author's assessments, not audit findings. But the README TLDR ("the governance frameworks don't address it") is more absolute than the underlying analysis supports.

---

## Summary

| Risk | Severity | Key question |
|------|----------|-------------|
| RR-01 Staleness | HIGH | When was this last reviewed? |
| RR-02 Source concentration | MEDIUM | How much comes from Anthropic's own disclosures? |
| RR-03 AI hallucination | MEDIUM | Has every factual claim been verified against its source? |
| RR-04 Single-author bias | HIGH | Who else has reviewed this analysis? |
| RR-05 Unverified sources | MEDIUM | Which claims depend on pending sources? |
| RR-06 Framework misreading | MEDIUM | Was the actual standard text consulted, or just summaries? |
| RR-07 Dual-use | LOW | Does this add attack information beyond what's already public? |
| RR-08 Scope creep | LOW | Does every piece of content serve the governance thesis? |
| RR-09 Vendor advocacy | LOW | Are product mentions descriptive or prescriptive? |
| RR-10 Temporal compression | HIGH | Was there a cooling-off period before publishing? |
| RR-11 Gap overstatement | MEDIUM | Would an auditor agree these are gaps, or just interpretation? |

---

*Created: 2026-04-08*
*Review cadence: Update when new content is added or when a risk status changes.*
