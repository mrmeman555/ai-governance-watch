# Repository Governance Controls

> **Purpose:** This repo advocates for governance rigor — it should demonstrate it. These controls govern the research itself: how claims are sourced, how content is reviewed, and how errors are handled.

---

## Source Integrity

### RC-01 — Unsourced Claims

**Risk:** A factual claim is published without a link to a primary or secondary source.

**Control:** Every factual claim must include:
1. A hyperlink to the source
2. A short description of what the source says (not just the title)

**Evidence check:** Can a reader verify the claim without leaving the repo? If no — it fails RC-01.

**Scope:** Applies to event briefs and framework docs. Analysis docs may contain editorial interpretation but must label it as such (see RC-05).

---

### RC-02 — Source Misrepresentation

**Risk:** A source is linked but the claim doesn't match what the source actually says. Common causes: paraphrasing drift, AI summarization error, outdated source content.

**Control:** Source descriptions must reflect what the source says, not what we want it to say. When updating a claim, re-read the source — don't rely on memory or prior summaries.

**Evidence check:** Does the linked source actually support the specific claim made? If the source says "may" and the claim says "will" — it fails RC-02.

---

### RC-03 — Link Rot

**Risk:** Source URLs go dead over time. Claims become unverifiable.

**Control:** Key links should include enough context (author, publication, date, title) that the source can be found even if the URL breaks. For critical sources (system cards, announcements), note the publication date and publisher.

**Review cadence:** Links checked quarterly. Dead links flagged in CHANGELOG and either updated or annotated with `[link dead as of YYYY-MM-DD]`.

---

## Content Quality

### RC-04 — Unreviewed AI Output

**Risk:** AI-generated content is published without human review. AI models hallucinate, misattribute, and fabricate plausible-sounding details.

**Control:** All content is AI-assisted but human-reviewed before publication. The attribution line at the bottom of README.md discloses this: "Writing assisted by Claude (Anthropic)."

**Evidence check:** Every commit should represent content the author has read and approved. Bulk AI-generated content pushed without review fails RC-04.

---

### RC-05 — Fact/Opinion Blending

**Risk:** Factual claims and editorial analysis are mixed without clear distinction. A reader can't tell what's documented fact vs. the author's interpretation.

**Control:** Use consistent labeling:
- **Event briefs** (`events/`) = factual. What happened, who said what, what the source says.
- **Analysis docs** (`analysis/`) = interpretation. Clearly framed as editorial ("this suggests," "the implication is," "this seems like").
- **Framework docs** (`frameworks/`) = factual gap identification + recommended interpretation. "Current language" vs. "Gap/finding" sections separate what the framework says from what we think it means.

**Evidence check:** Could a reader highlight every sentence in an event brief and trace it to a source? If not, it's opinion and belongs in analysis/.

---

### RC-06 — Stale Findings

**Risk:** A framework gap or event detail has been addressed (e.g., ISO 42001 issues a revision, a vulnerability gets patched) but the repo still presents it as current.

**Control:** Framework docs include a "Last updated" date. When a finding is resolved, it's moved to a "Resolved" section with the date and what changed — not silently deleted.

**Review cadence:** Framework docs reviewed when a relevant standards body publishes an update. CHANGELOG logs the review even if nothing changed ("Reviewed ISO 42001 — no updates").

---

## Provenance

### RC-07 — Production Opacity

**Risk:** Unclear how content was produced — which model was used, what sources were consulted, whether output was human-edited.

**Control:**
- README attribution discloses AI assistance
- CHANGELOG logs what was added and when
- Event briefs list all sources consulted in the Source section
- This repo's full production history is available in git commit history

---

### RC-08 — Correction Avoidance

**Risk:** An error is discovered but not corrected, or corrected silently without disclosure.

**Control:** When an error is found:
1. Fix it in the relevant file
2. Log the correction in CHANGELOG with what was wrong and what was changed
3. If the error was in a published event brief, add a correction note at the bottom: `*Correction (YYYY-MM-DD): [what changed and why]*`

Silent edits to factual claims fail RC-08.

---

## Scope

### RC-09 — Completeness Gap

**Risk:** Making broad claims ("frameworks don't address this") without disclosing what was actually checked.

**Control:** When claiming a gap exists across frameworks, list which frameworks were checked and which weren't. The `frameworks/` directory serves as the explicit scope — if a framework isn't listed there, we haven't assessed it.

**Example of what fails:** "No governance framework addresses harness-level controls" without specifying which frameworks were reviewed.

**Example of what passes:** "ISO 42001 (8.2, A.5, A.7), NIST AI RMF (GOVERN 2.1, MEASURE 2.6), and SOC 2 TSC lack harness-level controls. HITRUST AI Security Assessment partially addresses this with 51 AI-specific controls but relies on inheritance."

---

### RC-10 — Selection Bias

**Risk:** Cherry-picking events or findings that support the narrative while ignoring contradictory evidence.

**Control:** When a development contradicts or complicates the thesis, include it. The repo tracks what's happening — not what we wish were happening.

**Examples of what should be included even if inconvenient:**
- A framework revision that addresses a gap we documented
- A counterargument to the "reasonable security baseline" thesis
- An event that suggests the harness governance gap is narrowing

**Evidence check:** Has the repo ever documented something that weakened its own thesis? If not, ask whether that's because nothing has — or because it wasn't included.

---

## Summary

| Control | Risk | Key question |
|---------|------|-------------|
| RC-01 | Unsourced claims | Can a reader verify this claim from the linked source? |
| RC-02 | Source misrepresentation | Does the source actually say what we claim it says? |
| RC-03 | Link rot | Can the source still be found if the URL breaks? |
| RC-04 | Unreviewed AI output | Did a human read this before it was published? |
| RC-05 | Fact/opinion blending | Can a reader tell what's sourced fact vs. interpretation? |
| RC-06 | Stale findings | Is this still current, or has the landscape changed? |
| RC-07 | Production opacity | Is it clear how this content was produced? |
| RC-08 | Correction avoidance | When we're wrong, do we say so? |
| RC-09 | Completeness gap | Did we disclose what we checked and what we didn't? |
| RC-10 | Selection bias | Have we included evidence that complicates the thesis? |

---

*Added: 2026-04-08*
