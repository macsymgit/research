---
name: Western Electrical vs. Waterloo Architectural Engineering Comparison
description: Design spec for a side-by-side research comparison of Western University BESc Electrical Engineering and University of Waterloo BASc Architectural Engineering, in English and Chinese.
type: research-doc
status: draft
date: 2026-04-26
---

# Spec — Western EE vs. Waterloo ArchE Comparison

## 1. Goal

Produce a decision-grade side-by-side comparison of two CEAB-accredited Ontario engineering programs:

- **Western University (UWO)** — BESc Electrical Engineering (4-year, optional internship)
- **University of Waterloo** — BASc Architectural Engineering (5-year, mandatory co-op)

Output mirrors the depth and structure of the existing `waterloo-arch-comparison.md` so a reader who has used the existing comparison feels at home.

## 2. Out of Scope

- Other electrical-adjacent programs (Computer Eng, Mechatronics, Software Eng).
- Non-Ontario or non-CEAB schools.
- Other Western engineering streams (Mechanical, Civil, Chemical, Integrated).
- Graduate study pathways beyond a brief mention in the licensing section.
- 3D Animation / non-engineering programs already covered elsewhere in the repo.

## 3. Files to Produce

| Path | Language | Audience |
|------|----------|----------|
| `western-electrical-vs-waterloo-architectural-engineering.md` | English | Primary |
| `western-electrical-vs-waterloo-architectural-engineering-zh.md` | Simplified Chinese | Parents / family review |

The Chinese version is a faithful translation of the English version with localized framing where appropriate (e.g., currency notes, family-decision language consistent with `waterloo-arch-comparison-zh.md`).

## 4. Document Structure (mirrors waterloo-arch-comparison.md)

1. **30-Second Summary** — at-a-glance comparison table (school, identity, length, license, entry salary, co-op, employer demand, the trade-off).
2. **Program Fundamentals** — degree conferred, length, faculty, campus, co-op model, cohort size, ranking, accreditation, unique features.
3. **Admission Requirements** — Grade 12 cutoffs, required courses (Calculus, Vectors, Physics, Chemistry, English), supplementary applications (AIF for Waterloo; Western's admission process), competitive averages, Ontario applicant focus.
4. **Co-op and Work Experience** — Western EDI (optional, ≤16 months) vs. Waterloo mandatory co-op (5 terms, ~20 months). Salary ranges per term, employer types, sequencing.
5. **Curriculum: What You Actually Learn** — Year-by-year breakdown for each program. Western EE: circuits, signals, electromagnetics, power, control, electives in AI/comms/photonics. Waterloo ArchE: structures, building systems (HVAC, electrical, plumbing), envelope, sustainability, design studio every term.
6. **Professional Licensing Pathways** — Both lead to P.Eng. via PEO. EIT requirements, ~3 years experience post-grad. Note: Waterloo ArchE grads also commonly pursue LEED AP / WELL credentials.
7. **Career Outcomes and Salaries** — Job titles, entry salaries (sourced from Job Bank Canada and Salary Expert), 5-year and 10-year trajectories, sectors of employment.
8. **Job Market Outlook (2025–2030)** — Demand projections (BuildForce Canada for ArchE-relevant trades; Job Bank for electrical engineers). AI/automation impact on each discipline. Geographic hotspots.
9. **Student Life and Culture** — London vs. Waterloo/Cambridge, residence options, student engineering societies (Western Engineering Students' Society vs. Waterloo Engineering Society), workload culture (5-day vs. 4-month rotation), city size and cost of living.
10. **Cost and Financial Comparison** — Tuition (Ontario domestic), residence, ancillary fees, projected total program cost, co-op earnings offset, 4-year net cost vs. 5-year net cost (with co-op income factored in).
11. **Decision Framework: Which Is Right for You?** — Question-driven framework (12 questions): scope of interest, hands-on vs. theoretical, mandatory work experience preference, geographic preference, salary ceiling vs. mission, AI/automation comfort, family budget, etc. Each question maps to a recommendation.
12. **Master Comparison Table** — Single dense table summarizing every dimension above for quick reference.

## 5. Key Asymmetries to Surface Honestly

The comparison is NOT symmetric. Surface these tensions explicitly rather than paper over them:

1. **Co-op model** — Western EDI is *optional*; Waterloo ArchE co-op is *mandatory and structurally embedded*. This drives differences in time-to-graduate, total work experience at graduation, and net program cost.
2. **Discipline breadth** — Electrical Engineering is one of the broadest engineering disciplines (power, signals, electronics, communications, embedded, AI hardware, photonics). Architectural Engineering is narrowly scoped to the building industry. This affects salary ceiling, geographic mobility, and recession resilience.
3. **Salary ceiling** — EE has a higher long-term ceiling (esp. tech/semiconductors/AI hardware). ArchE has a more predictable mid-career trajectory tied to construction cycles.
4. **City/campus** — London (mid-size, lower cost of living, smaller co-op employer pool) vs. Waterloo/Cambridge (tech corridor, larger employer pool, higher cost of living).
5. **AI/automation exposure** — Both face AI exposure but differently: EE may *build* the AI hardware; ArchE may have building-design tasks partially automated by generative tools. Cite Anthropic Economic Index v4 for occupational exposure data where applicable.
6. **Licensing** — Symmetric. Both → P.Eng. via PEO in ~3 years post-grad. Don't overweight this section.

## 6. Sources and Citation Standards

Maintain the repo's citation discipline. Allowed authoritative sources:

- **uwaterloo.ca** — Waterloo ArchE program pages, calendar, co-op stats.
- **uwo.ca / www.eng.uwo.ca / welcome.uwo.ca / registrar.uwo.ca** — Western EE program, admission, EDI internship.
- **engineerscanada.ca** — CEAB accreditation status.
- **peo.on.ca** — P.Eng. licensing pathway.
- **www.jobbank.gc.ca** — Wages, employment outlook by NOC code (NOC 21310 Electrical/Electronics Engineers; NOC 21300 Civil Engineers / 22300 Civil Eng Technologists for ArchE-adjacent). Verify NOC codes against the 2021 NOC reference at the time of writing.
- **www.salaryexpert.com** — Salary distributions where Job Bank is sparse.
- **www.buildforce.ca** — Construction sector outlook for ArchE.
- **www.cagbc.org** — LEED relevance for ArchE.
- **uwimprint.ca / on-sitemag.com / newengineer.com** — Supporting context.
- **WebSearch** — Allowed for cross-checking and finding non-allowlisted official pages; cite the original authoritative URL.
- **Anthropic Economic Index v4** — Not on the WebFetch allowlist. Accessed via the local NotebookLM workflow already permitted in `.claude/settings.local.json` (`scripts/run.py ask_question.py …`). Cite as "Anthropic Economic Index v4 (Jan 2026)" with the relevant section.

Every quantitative claim (salary, tuition, co-op term length, cohort size, ranking) must carry a footnote-style citation. Soft qualitative claims ("design culture," "city feel") may be uncited but should be hedged.

## 7. Tone and Style

- Match the existing repo voice: factual, decision-oriented, hedged where data is uncertain.
- Use present tense for current program facts; future tense only where projecting (with explicit hedge).
- Avoid marketing language from either institution. Surface trade-offs, not advantages-only lists.
- 30-second summary must be honestly bidirectional — a reader leaning either way should see why their lean is reasonable.
- Chinese version: use the same family-decision framing as `waterloo-arch-comparison-zh.md`.

## 8. Acceptance Criteria

The English doc is acceptable when:

1. All 12 sections are present in the order above.
2. Every numeric claim has a citation to an allowlisted source.
3. Asymmetries from §5 are surfaced explicitly, not buried.
4. Master comparison table at the end covers every dimension discussed in narrative.
5. Decision framework section produces a recommendation (not just questions).
6. Length is comparable to `waterloo-arch-comparison.md` in *depth per dimension*. Total length may be proportionally shorter because this is a 2-way comparison vs. the existing 3-way doc — a column drops out of every table.

The Chinese doc is acceptable when:

1. It is a faithful translation, not an abridgement.
2. Currency, dates, and units are presented in Chinese-reader-friendly form (CAD noted, dates in YYYY-MM-DD, etc.).
3. Citations: keep the original English-source URLs inline in the ZH doc (do not translate URLs or invent Chinese-language equivalents). Follow the established pattern in `waterloo-arch-comparison-zh.md`.

## 9. Open Risks

- **Western EE data freshness** — Western may have curriculum changes for 2026 entry not yet indexed; rely on the most recent academic calendar and flag uncertainty in footnotes.
- **EDI internship participation rate** — If Western publishes participation data only sporadically, hedge claims about "typical" Western EE work experience.
- **Job Bank NOC mapping for ArchE** — ArchE doesn't map cleanly to one NOC code; use a blended estimate from civil + mechanical + electrical engineering NOCs and disclose the methodology.

## 10. Out-of-Spec Follow-ups (Not in This Round)

- Comparison vs. Toronto Metropolitan / McMaster / Queen's EE.
- Comparison vs. UWaterloo Electrical Engineering (same school, different program).
- Update to README.md table of contents — leave for the implementation plan.
