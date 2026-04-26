# Western EE vs. Waterloo ArchE Comparison — Implementation Plan

> **For agentic workers:** REQUIRED: Use superpowers:subagent-driven-development (if subagents available) or superpowers:executing-plans to implement this plan. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Produce a side-by-side comparison of Western University BESc Electrical Engineering and University of Waterloo BASc Architectural Engineering, in English and Simplified Chinese, mirroring the structure of the existing `waterloo-arch-comparison.md` doc.

**Architecture:** Pure markdown deliverables in a research repo. No code, no build, no tests. The "TDD" rhythm is replaced by a **research → draft → cite-check → commit** cycle, one section at a time, so each commit lands a citable, decision-grade chunk.

**Tech Stack:** Markdown. WebFetch (allowlisted domains in `.claude/settings.local.json`), WebSearch (cross-checks). Existing repo docs as parallel templates: `waterloo-arch-comparison.md`, `waterloo-architectural-engineering.md`, `waterloo-arch-comparison-zh.md`.

**Spec:** `docs/superpowers/specs/2026-04-26-western-ee-vs-waterloo-arche-comparison-design.md`

**Conventions for every step in this plan:**
- Cite every numeric claim. Quote the URL inline with the data point.
- Hedge soft claims ("typical," "around"). Don't fabricate precision.
- After each section is drafted, scan it for: TODOs, "TBD", uncited numbers, fabricated URLs/DOIs. Fix before commit.
- Never invent a URL, citation, or quoted figure. If a source can't be found, write "Not publicly disclosed" or hedge the claim — never fill the gap with plausible-looking fiction.
- Commits are scoped per chunk (not per section), to keep history readable.
- Reuse existing repo content where overlap exists (Waterloo ArchE program facts already live in `waterloo-architectural-engineering.md` — pull from there, don't re-research).

**File map:**
| Action | Path | Purpose |
|--------|------|---------|
| Create | `western-electrical-vs-waterloo-architectural-engineering.md` | English deliverable |
| Create | `western-electrical-vs-waterloo-architectural-engineering-zh.md` | Chinese deliverable |
| Modify | `README.md` | Add new docs to the index |

---

## Chunk 1: Research Data Gathering (Western EE)

**Objective:** Collect every Western EE fact needed before drafting starts. Waterloo ArchE facts are already in the repo — only Western data needs net-new research.

**Files:**
- Scratch notes will be kept in conversation context, not committed. Final citations land directly in the EN doc during drafting chunks.

- [ ] **Step 1.1: Fetch Western EE program overview**

Run: WebFetch on `https://www.eng.uwo.ca/electrical/undergrad/index.html` (or current canonical URL — confirm via WebSearch first).
Capture: degree name, length, accreditation body, faculty, total credits, available electives/specializations.

- [ ] **Step 1.2: Fetch Western admission requirements**

Run: WebFetch on Western's admission page for engineering. WebSearch first for the canonical URL.
Capture: required Grade 12 courses (English, Calculus + Vectors, Chemistry, Physics, plus Advanced Functions if separate), competitive average for Engineering Year 1 entry, supplementary application status. For entrance average, capture the published *range* (e.g., "low-to-mid 80s") with explicit hedge — Western typically publishes a range, not a single per-cycle number. Do not fabricate a precise number to fill a cell.

- [ ] **Step 1.3: Fetch Western EDI internship details**

Run: WebFetch on Western Engineering's internship/EDI program page.
Capture: program name (Engineering Discovery & Internship or current branding), optional vs. mandatory, length (12–16 months), eligibility year, typical placement sectors, participation rate if published.

- [ ] **Step 1.4: Fetch Western EE curriculum (year-by-year)**

Run: WebFetch on Western academic calendar / EE program of study.
Capture: required courses by year, specialization streams (Power Systems, Communications, Embedded, Photonics, Biomedical, etc.), typical electives, capstone/design project structure.

- [ ] **Step 1.5: Fetch Western tuition and fees**

Run: WebFetch on `registrar.uwo.ca` or Western fees page for Ontario domestic engineering tuition.
Capture: annual tuition, ancillary fees, residence cost range, meal plan range, books/supplies estimate. Use most recent published year.

- [ ] **Step 1.6: Fetch CEAB accreditation status**

Run: WebFetch on `engineerscanada.ca` for the current accreditation list. Confirm Western EE is CEAB-accredited and note expiry/renewal year.

- [ ] **Step 1.7: Fetch electrical engineer salary data (Job Bank)**

Run: WebFetch on `www.jobbank.gc.ca` wage report for NOC 21310 (Electrical and electronics engineers), Ontario.
Capture: low / median / high wages, employment outlook (Good / Fair / Limited), 2024-2026 projection.

- [ ] **Step 1.8: Fetch ArchE-relevant salary data (Job Bank)**

Run: WebFetch on Job Bank wage reports for NOC 21300 (Civil engineers) and NOC 22300 (Civil engineering technologists), Ontario, as proxies. Note that ArchE doesn't map cleanly — disclose this in the doc.
Capture: low / median / high wages.

- [ ] **Step 1.9: Verify Waterloo ArchE facts already in repo**

Run: Read `waterloo-architectural-engineering.md` end-to-end. Note which facts can be lifted directly (program length, co-op terms, cohort size, tuition, salaries) and confirm citation freshness. If a citation is older than 12 months and a newer source exists, refresh it during drafting.

- [ ] **Step 1.10: Verify allowlist covers Western domains**

Read `.claude/settings.local.json`. Confirm it includes `WebFetch(domain:www.eng.uwo.ca)`, `WebFetch(domain:uwo.ca)`, `WebFetch(domain:welcome.uwo.ca)`, `WebFetch(domain:registrar.uwo.ca)`, and `WebFetch(domain:www.salaryexpert.com)` (already pre-staged). If any are missing, add them and explicitly include the file in the next commit.

- [ ] **Step 1.11: Commit research scaffolding (allowlist + spec + plan)**

```bash
git add .claude/settings.local.json docs/superpowers/specs/2026-04-26-western-ee-vs-waterloo-arche-comparison-design.md docs/superpowers/plans/2026-04-26-western-ee-vs-waterloo-arche-comparison.md
git commit -m "$(cat <<'EOF'
Add spec and plan for Western EE vs Waterloo ArchE comparison

Adds design spec, implementation plan, and Western University WebFetch
domains to the allowlist so the research data can be sourced directly
from official Western pages.

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
EOF
)"
```

Expected: clean commit with spec + plan + settings change.

---

## Chunk 2: English Doc — Sections 1–6

**Objective:** Draft the front half of the English deliverable: summary, fundamentals, admissions, co-op, curriculum, licensing.

**Files:**
- Create: `western-electrical-vs-waterloo-architectural-engineering.md`

- [ ] **Step 2.1: Scaffold the EN doc with title, date, TOC, and section headings**

Create the file with:
- Title: `# Western Electrical Engineering vs. Waterloo Architectural Engineering: Complete Comparison`
- Subtitle line: `> **Research date**: April 2026 | A side-by-side comparison of two CEAB-accredited Ontario engineering programs`
- Table of Contents listing the 12 sections from the spec.
- Section heading stubs (no content yet) for sections 1–12 with anchors that match the TOC.

Verify: run a markdown link check by visually scanning that each TOC entry's anchor matches the section heading slug.

- [ ] **Step 2.2: Draft Section 1 — 30-Second Summary**

Write the table with rows: School, Core identity, Degree type, Total time, License, Entry salary, Co-op model, Employer demand, The trade-off.
Two columns: **Western EE (BESc)**, **Waterloo ArchE (BASc)**.

Source numbers from Chunk 1 research. Inline-cite each numeric cell.

- [ ] **Step 2.3: Draft Section 2 — Program Fundamentals**

Table covering: Degree conferred, Length, Faculty, Campus, Co-op/internship model, Cohort size, Accreditation, Unique features, Program maturity.

Surface explicitly: Western EDI is *optional*; Waterloo ArchE co-op is *mandatory*.

- [ ] **Step 2.4: Draft Section 3 — Admission Requirements**

Table with: Required Grade 12 courses, Minimum competitive average, Supplementary application (Western's process vs. Waterloo's AIF), Acceptance rate (if published — otherwise hedge), Most recent cohort entrance average.

If Western or Waterloo do not publish a stat, write "Not publicly disclosed" — never fabricate.

- [ ] **Step 2.5: Draft Section 4 — Co-op and Work Experience**

Two subsections, one per program. For each: program name, optional vs. mandatory, total duration, term length, typical earnings per term (cite Job Bank or program pages), employer types, sequencing relative to academic terms.

End the section with a "What this means for your résumé at graduation" paragraph contrasting ~20 months guaranteed (Waterloo) vs. ≤16 months optional (Western).

- [ ] **Step 2.6: Draft Section 5 — Curriculum**

Year-by-year breakdown for each program in parallel two-column layout.
Western EE: highlight specialization streams (Power, Communications, Embedded/AI hardware, Photonics, Biomedical) and the Year 4 capstone.
Waterloo ArchE: highlight design studio every term, Year 3 in Cambridge, building systems integration, Year 5 thesis.

End with a "Where the curricula overlap and diverge" paragraph (electrical/lighting in both; structures only in ArchE; signals/comms only in EE; design studio only in ArchE).

- [ ] **Step 2.7: Draft Section 6 — Professional Licensing Pathways**

Both → P.Eng. via PEO. Walk through: degree → EIT registration → 48 months experience (12 months Canadian) → PPE exam → P.Eng. licensure. Note that Waterloo ArchE grads commonly add LEED AP or WELL credentials; Western EE grads commonly add PMP or specialty certifications (e.g., IEEE certifications).

Cite peo.on.ca for licensing requirements.

- [ ] **Step 2.8: Cite-check Sections 1–6**

For each numeric claim in 1–6, verify the inline citation URL is on the allowlist, resolves to the cited page, and supports the specific number. Replace any that don't.

- [ ] **Step 2.9: Commit Chunk 2**

```bash
git add western-electrical-vs-waterloo-architectural-engineering.md
git commit -m "$(cat <<'EOF'
Draft EN comparison: sections 1-6 (summary through licensing)

Covers Western BESc Electrical Engineering vs Waterloo BASc Architectural
Engineering through professional licensing. Sections 7-12 (career, market,
finance, decision framework, master table) follow in the next commit.

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
EOF
)"
```

---

## Chunk 3: English Doc — Sections 7–12

**Objective:** Draft the back half: career outcomes, job market, student life, cost, decision framework, master table.

**Files:**
- Modify: `western-electrical-vs-waterloo-architectural-engineering.md`

- [ ] **Step 3.1: Draft Section 7 — Career Outcomes and Salaries**

Two-column table: typical entry-level job titles, entry salary range, 5-year median, 10-year median, top employers, sector breakdown.
Western EE: tech, semiconductor, utilities, telecom, defense, consulting.
Waterloo ArchE: building consulting (Arup, RWDI, WSP), developers, mechanical/electrical engineering firms, sustainability consultancies.

Cite Job Bank for entry salaries; Salary Expert for 5-year/10-year medians. Hedge ArchE long-term medians given the cleaner-NOC issue (disclose method).

- [ ] **Step 3.2: Draft Section 8 — Job Market Outlook (2025–2030)**

Demand projections per program. Cite Job Bank's outlook for NOC 21310 (electrical engineers) and BuildForce Canada for construction-sector demand. Geographic hotspots (Western EE: Ottawa/Toronto/Waterloo for tech; Waterloo ArchE: Toronto/GTA/Vancouver for building consulting).

AI/automation paragraph: cite Anthropic Economic Index v4 (Jan 2026) via the local NotebookLM workflow. Exact command to run (from repo root):

```bash
python scripts/run.py ask_question.py --question "What does the report say about AI exposure for electrical engineers and architectural/civil engineers? Cite specific occupational exposure percentages and the augmentation-vs-automation split." --notebook-url "https://notebooklm.google.com/notebook/8fac3361-8a7d-4f05-a618-54ce40f3e09e"
```

Use the returned answer with explicit attribution (`per Anthropic Economic Index v4, Jan 2026`); hedge with the AEI's own "augmentation vs. automation" framing.

- [ ] **Step 3.3: Draft Section 9 — Student Life and Culture**

London (Western) vs. Waterloo/Cambridge (UWaterloo). Cover: campus feel, residence options, student engineering societies, workload culture, city size, public transit, cost-of-living index. Use uwo.ca and uwaterloo.ca for residence/society facts; cite a single salary/cost-of-living source for COL claims.

- [ ] **Step 3.4: Draft Section 10 — Cost and Financial Comparison**

Table: annual tuition, residence, ancillary fees, books, total per year, projected total program cost (4 yr Western / 5 yr Waterloo).
Then a "Net cost after co-op earnings" paragraph: Waterloo's mandatory ~20 months of co-op income offsets a substantial portion of program cost; Western EDI participants get an offset only if they opt in.

Provide a worked example with explicit assumptions ("If a Waterloo ArchE student earns $24/hr × 35 hrs × 16 weeks × 5 terms = …").

- [ ] **Step 3.5: Draft Section 11 — Decision Framework**

12 decision questions, each with: the question, what each answer suggests (Western EE or Waterloo ArchE), and rationale.
Examples: "Do you want broad disciplinary scope or focused specialization?" "Is mandatory paid work experience a hard requirement?" "Do you prefer a tech-corridor co-op employer pool or a smaller-city campus feel?"

End the section with a short "If you're still torn" paragraph.

- [ ] **Step 3.6: Draft Section 12 — Master Comparison Table**

Single dense table (~30 rows) summarizing every dimension from Sections 2–10. Two columns. Each row is one fact + one citation marker.

- [ ] **Step 3.7: Add Sources footer**

After Section 12, add a `## Sources` section listing every URL cited in the doc, grouped by category (Western Programs / UWaterloo Programs / Salary Data / Licensing / Market Outlook / AI Impact). Use numbered footnote-style links.

- [ ] **Step 3.8: Cite-check Sections 7–12 + Sources**

For each numeric claim, verify the inline citation. Verify every URL in the Sources footer resolves and is on the allowlist (or is documented as a non-allowlist source per the spec, e.g., AEI v4).

- [ ] **Step 3.9: Read the full EN doc end-to-end**

Read top to bottom checking: TOC anchors all match, no orphan TODOs, no contradictions between sections (e.g., Section 1 summary vs. Section 7 detail), tone is consistent and decision-oriented.

- [ ] **Step 3.10: Commit Chunk 3**

```bash
git add western-electrical-vs-waterloo-architectural-engineering.md
git commit -m "$(cat <<'EOF'
Complete EN comparison: sections 7-12 + sources

Career outcomes, 2025-2030 job market outlook, student life, cost
analysis with co-op offset modeling, 12-question decision framework,
master comparison table, and sources footer.

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
EOF
)"
```

---

## Chunk 4: Chinese Translation

**Objective:** Produce the `-zh` companion. Faithful translation, not abridgement, matching the family-decision framing of `waterloo-arch-comparison-zh.md`.

**Files:**
- Create: `western-electrical-vs-waterloo-architectural-engineering-zh.md`
- Reference: `waterloo-arch-comparison-zh.md` (style template)

- [ ] **Step 4.1: Re-read the Chinese template**

Read `waterloo-arch-comparison-zh.md` end-to-end to lock in: terminology choices (e.g., 建筑工程学 for Architectural Engineering, 电气工程 for Electrical Engineering, 带薪实习 for co-op, 注册工程师 for P.Eng.), header style, table formatting, citation handling.

- [ ] **Step 4.2: Translate scaffolding (title, date line, TOC, section headings)**

Title: `# 西安大略大学电气工程学 vs. 滑铁卢大学建筑工程学：完整对比`

**Canonical Chinese name decision (locked):** Use **西安大略大学** for Western University throughout the doc. Rationale: this is the form used on Western's own Chinese-language pages and is the more recognizable name to PRC-educated parents. Do not switch to 韦仕敦大学 mid-doc.

Subtitle: `> **研究日期**：2026年4月 | 安大略省两个CEAB认证工程项目的横向对比`

Translate all 12 section headings to match the existing `-zh` convention.

- [ ] **Step 4.3: Translate Sections 1–6**

Translate the EN content section-by-section. Keep:
- All numeric data unchanged.
- All URLs unchanged (do NOT translate URLs).
- CAD currency notation explicit ("$72,000 加元").
- Acronyms with first-mention parenthetical Chinese expansion (e.g., "P.Eng.（专业工程师执照）", "CEAB（加拿大工程认证委员会）").

- [ ] **Step 4.4: Translate Sections 7–12 + Sources footer**

Same conventions. The 12 decision questions in Section 11 should read naturally to a Chinese-speaking parent — adapt phrasing where literal translation would be awkward, but keep the question semantics intact.

- [ ] **Step 4.5: Cross-check ZH vs. EN**

Spot-check: pick 5 random numeric claims and confirm they match the EN doc exactly. Confirm no URLs were corrupted. Confirm terminology consistency throughout (e.g., always 建筑工程学, never sometimes 建筑工程 alone).

- [ ] **Step 4.6: Commit Chunk 4**

```bash
git add western-electrical-vs-waterloo-architectural-engineering-zh.md
git commit -m "$(cat <<'EOF'
Add Chinese translation of Western EE vs Waterloo ArchE comparison

Faithful translation of the EN doc following the family-decision framing
established in waterloo-arch-comparison-zh.md.

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
EOF
)"
```

---

## Chunk 5: README Update and Final Sweep

**Objective:** Make the new docs discoverable and do a last consistency pass.

**Files:**
- Modify: `README.md`

- [ ] **Step 5.1: Read current README**

Read `README.md` fully to find where the existing comparison docs are listed and how the entry style is formatted.

- [ ] **Step 5.2: Add EN + ZH entries to README**

Add two entries under the existing comparison-doc section, matching the established formatting. Each entry: title, one-line description, link.

- [ ] **Step 5.3: Final repo-wide sanity check**

Verify:
- Both new files are committed.
- README links resolve (relative paths correct).
- No accidental large binary or unrelated files staged.
- `git status` is clean after the README commit.

- [ ] **Step 5.4: Commit Chunk 5**

```bash
git add README.md
git commit -m "$(cat <<'EOF'
Index Western EE vs Waterloo ArchE comparison in README

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
EOF
)"
```

- [ ] **Step 5.5: Surface to user for review**

Print the list of new/changed files and the commit graph for this work, then stop. Do not push to remote without explicit user request.

---

## Done When

- Both deliverables exist on `main`.
- Every numeric claim in both docs has a working citation.
- README indexes both new docs.
- `git log` shows 5 focused commits (allowlist+spec+plan, EN-front, EN-back, ZH, README).
- User has been asked whether to push.
