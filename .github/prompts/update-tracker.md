# AI Governance Watch — automated update task

You are updating the **ai-governance-watch** research tracker. Produce a small, high-quality, **conservative** update and leave the working tree changed; a PR will be opened for human review. **Nothing you write is "published" — every claim must trace to a primary source, and a human reviews the PR before merge.**

## Ground rules
- **This repo is independent research, not compliance advice. Accuracy over volume.** If you cannot verify a development against a **primary source** (official announcement, regulator/standards-body publication, system card, court doc, or a reputable outlet citing one), do **not** add it.
- Add **0–3 new items per run.** Finding nothing genuinely new + significant is a *valid, good* outcome — make **no changes** and say so.
- **Match the repo's existing conventions exactly** — read the files before writing.

## Steps
1. **Orient.** Read `README.md`, `CHANGELOG.md` (its top entry = the last-update date = your cutoff), `SOURCES.md` (existing `[CITATION-KEY]`s), `templates/event-brief.md`, `templates/framework-update.md`, and list `events/`. Only consider developments **after** the cutoff.
2. **Research (since the cutoff).** Look for genuinely new, significant developments in: AI-agent capability disclosures (system cards, red-team/eval results), cyber-governance frameworks (SOC 2, HITRUST, HIPAA, ISO 42001, NIST AI RMF, EU AI Act, MITRE ATLAS, OWASP LLM/Agentic Top 10), AI-agent incidents/breaches, regulator/standards-body actions, and the Project Glasswing / Mythos thread. Prefer primary sources. **Dedup** against existing `events/` + `SOURCES.md` — skip anything already covered.
3. **Draft event brief(s).** For each new item: create `events/YYYY-MM--slug.md` from `templates/event-brief.md` (Title · Date · Source[primary URL] · What happened[2–3 paras] · Who's affected · Key links · `*Added: YYYY-MM-DD*` footer). Where an item changes a specific framework control, also fill `templates/framework-update.md` (Framework · Triggered-by[link to the event] · Control/section · Current language · Gap · Recommendation).
4. **Register citation keys** in `SOURCES.md` — add an uppercase-hyphenated `[KEY]` per new primary source, matching the existing format/section style.
5. **Update index surfaces:** add the item(s) to the README **"Latest"** table (newest first; same columns/format) and the events list; and prepend a **`CHANGELOG.md`** entry in the exact existing format (`## YYYY-MM-DD — <summary>` + `- Added/Updated <file> … [KEY]` bullets naming each file + citation key).
6. **Self-check:** every new claim cites a primary source; every new event appears in SOURCES + README + CHANGELOG; dates/links correct; tone matches the repo (no editorializing — claims trace to quotes). Print a short summary of what you added, or "No new developments — no changes."

## Constraints
- Edit only within `events/`, `analysis/`, `templates/` outputs, `SOURCES.md`, `README.md`, `CHANGELOG.md`. **Do not restructure the repo** or touch `.github/`.
- Be conservative: a credible-but-unverified rumor is **not** an event. When unsure, leave it out (you may note it in the run summary).
- Keep total new prose tight and sourced — this is a tracker, not a blog.
