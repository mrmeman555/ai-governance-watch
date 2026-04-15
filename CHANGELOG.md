# Changelog

All notable updates to this repository.

---

## 2026-04-14 — New event: SANS/CSA/OWASP Mythos-Ready Security Briefing

- Added `events/2026-04--sans-csa-owasp-mythos-briefing.md` — event brief for the emergency strategy briefing released today by SANS Institute, Cloud Security Alliance, [un]prompted, and the OWASP GenAI Security Project. Co-authored by former CISA Director Jen Easterly, former National Cyber Director Chris Inglis, Google CISO Phil Venables, and 60+ others; reviewed by 250+ CISOs. Direct link to 30-page PDF at `https://labs.cloudsecurityalliance.org/mythos-ciso/`.
- Updated `analysis/reasonable-security-baseline.md` — added "Practitioner Corroboration" section citing the briefing's Row 12 as the first primary-source practitioner document to articulate the Wyndham-to-Mythos "reasonable defensive effort" shift as an active governance and liability risk.
- Updated `SOURCES.md` — registered `[MYTHOS-BRIEFING]` citation key with both the GlobeNewswire press release and the PDF as primary sources.
- Updated `README.md` — added the new event to the events list.

---



- Added `analysis/disclosure-and-deployment.md` — framing piece on the simultaneity of the April 7 Glasswing announcement: capability disclosure, behavioral evidence, and ~50-organization enterprise deployment arrived in the same document. Argues that the governance review sequence assumed by ISO 42001, NIST AI RMF, and SOC 2 did not occur because disclosure and deployment were the same event.
- Updated README analysis section to include the new piece.

---

## 2026-04-09 — Reground in verbatim sources

- Created `system-card-summary.md` — single document with verbatim quotes and `[GLASSWING-CARD]` citations covering all 8 topic areas
- Rewrote all 3 analysis files to remove editorial voice — every claim now traces to a direct quote from a primary source
- Removed unverified claims (Mexico AI incident, unsourced insurance/PCAOB paragraphs, editorial predictions)
- Removed intermediate artifacts that didn't survive iteration: 8 individual system card workpapers, 5 framework trackers, controls directory, risk register, workpaper template

---

## 2026-04-08 — Restructure and system card integration

- Restructured from flat files into `events/`, `analysis/`, `templates/`
- Created 6 event briefs with standardized fields
- Created 3 analysis pieces connecting events to governance implications
- Integrated 244-page Mythos Preview system card (alignment assessment, exploit development, cost data)
- Added day-after coverage: NBC/Fortune/CyberScoop, FY2027 budget ($707M CISA cut), Section 702 FISA push
- Rewrote README with causal timeline, sourced every claim
- Created SOURCES.md with full bibliography and citation keys
- Renamed repo from `ai-security-governance` to `ai-governance-watch`

---

## 2026-04-08 — Initial publication

- Created repository with README, event timeline, and analysis
- Published as `ai-security-governance`
- Added attribution disclaimer
