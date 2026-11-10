---
name: program-research
description: Use when the user wants a comprehensive research report on a specific Canadian post-secondary program, or asks to research a program the same way as an existing report in this repo. Produces a ~70–80K-character report (admission, costs, professional pathway, curriculum, outcomes, AI impact, alternatives, year-by-year plan, ROI, decision framework) with live-source verification of every number, plus a paired Chinese (`-zh.md`) translation written in the same run without asking. Not for short comparisons or single-fact lookups.
---

# Program Research — Deep Dive

Produce comprehensive ~70–80K-character research reports on Canadian university programs, anchored to the format established in `mcmaster-life-sciences.md`.

## When to Use This Skill

Trigger when the user:
- Asks for "detailed research", "deep research", "comprehensive analysis", or "in-depth research" on a specific program
- Says "do the same as [existing report]" while referencing a report in this repo
- Names a specific Canadian post-secondary program (Waterloo, Western, McMaster, U of T, Queen's, McGill, etc.) and wants the full picture
- Asks for parent-facing or student-facing program write-ups with admission, costs, careers, ROI, and decision frameworks combined

Do NOT trigger for: short program comparisons, program lookups with a single specific question (just answer it), or non-Canadian programs unless the user explicitly opts in.

## The Core Pattern

A finished report has three properties that distinguish it from generic university research:

1. **Live-source verification.** Every numeric claim — tuition, salaries, employment rates, accreditation dates, outlook ratings — is fetched from an authoritative source and stamped with the verification month.
2. **Honest hedging.** When a source doesn't break out the data the reader needs (e.g., per-program cohort size, or a Job Bank NOC code that's a proxy for the actual occupation), the report says so explicitly with phrases like "hedged caveat" or "the source does not capture X." This is more useful than confident-sounding guesses.
3. **What this means for you.** Each analytical section ends with a practical implication for a prospective student, not just data. The reader should never have to ask "so what?"

If a draft lacks any of these three, it's not done.

## Workflow

### Step 1 — Gather the source base

Before writing, do the following in parallel where possible:

1. **Read existing repo material on the program.** The repo may already hold a report, plan, or schedule that covers it. Extract every cited number and URL. Do not duplicate research the repo already has.
2. **Web-fetch the program's official future-students / undergraduate page** for: prerequisites, admission averages, cohort statistics, supplementary application requirements, co-op/internship structure, specializations.
3. **Web-fetch the program's faculty co-op or career-centre page** for: hourly wages, average salaries, employer lists, employment rates.
4. **Web-fetch Job Bank** for the relevant NOC code(s): Ontario wages (low/median/90th percentile + Toronto sub-median) and the current outlook rating with the period it covers. Note the wage-update date and the outlook-update date.
5. **Web-fetch Engineers Canada / accreditation registry** if the program is engineering — confirm CEAB accreditation year and current status.
6. **Web-fetch the licensing body** (PEO for engineering, OAA for architecture, OMSAS / med-school regulators, etc.) for licensing requirements, exam pass rates, and timeline.
7. **Web-fetch industry-forecast sources** as relevant (BuildForce Canada, CAGBC, CMHC, sector-specific reports). Capture forecast horizons and methodology hedges.

The repo's `.claude/settings.local.json` allowlists the authoritative domains. Stay within the allowlist for primary verification. See `references/source-allowlist.md` for the full mapping of program type → authoritative sources.

### Step 2 — Write the document

Use the 15-section structure documented in `references/document-template.md`. The skeleton:

1. **Executive Summary** — TL;DR for parents, TL;DR for students, Core Numbers at a Glance, "Three Things Most Applicants Get Wrong"
2. **Program Overview** — Faculty, what the program actually means, demographics, class size, distinguishing structural features
3. **Admission Requirements & Costs** — Prerequisites, AIF/supp app, IB/AP, international, tuition, residence, total 4–5 year cost, OSAP, net cost after work-experience offset
4. **Professional Pathway** — P.Eng. for engineering, Med school for pre-med, OAA for architecture, no-license for unregulated programs. Include the licensing body, exam, experience requirements, and total HS-to-credential timeline.
5. **Co-op or Internship Detail** — Mandatory vs. optional, sequence, employer types, salary tables, how it counts toward licensing
6. **Curriculum** — Year-by-year arc, specializations, software/tools, divergence from related programs
7. **Graduate Employment, Salaries & Realistic Outcomes** — Entry / median / 90th percentile, sector breakdown, geographic distribution, realistic probability of each milestone
8. **Job Market & AI Analysis** — NOC outlook, demand drivers, BuildForce / industry forecasts, Anthropic Economic Index v4 group data, regulatory floor against AI displacement
9. **Alternative Career Pathways** — Every realistic pivot with cost, timeline, and salary signal
10. **Year-by-Year Action Plan** — Y1 → Y4 or Y5, with single dominant goal, high-leverage actions, and success benchmarks per year
11. **Success Tactics** — GPA, networking, AI tooling, financial, mental health
12. **Financial Trajectory & ROI Analysis** — Gross cost, work-experience offset, net cost, 5-year and 10-year and 25-year trajectories
13. **Decision Framework** — 12-question matrix, who should / shouldn't, overall verdict
14. **Quick Stats Table** — One-page reference of all numbers
15. **Sources** — Grouped by category (program/admission, accreditation, salary, industry, AI), with inline URLs

This template, not the anchor's section list, sets the structure. `mcmaster-life-sciences.md` is an 11-section pre-med variant: it folds Curriculum into Program Overview, replaces Sections 5–8 with a Realistic Probability Analysis, and has no Quick Stats Table. Drop a section only when it cannot apply (e.g., no co-op); say so in the Table of Contents.

Target length: **~70–80K characters**; `mcmaster-life-sciences.md` is about 81K characters. Shorter reports skip detail the user has explicitly asked for; longer reports include filler that dilutes the verification work.

### Step 3 — Voice and style

The voice has six characteristics (`mcmaster-life-sciences.md` shows all but the italic callouts):

1. **Inline citations** with `[domain](URL)` format — e.g., `([Job Bank](https://www.jobbank.gc.ca/...))`. Every numeric claim should have a citation or an explicit hedge.
2. **Hedging language** — "hedged caveat", "the source does not break out X", "treat as approximate", "triangulated from..." Never claim a precise number you can't trace; say what you do and don't know.
3. **Worked examples** with explicit assumptions — when computing co-op earnings or net cost, show the math: hours per term × hourly rate × number of terms = total. Give a low and high bound rather than a single number.
4. **"What this means for you"** framing — close analytical sections with a paragraph that translates the data into a recommendation or a constraint, addressed to a specific reader (prospective student, parent, applicant deciding between two programs).
5. **Bottom-line callouts** in italicized blockquotes for the verdict at the end of major sections (Decision Framework verdict, Overall verdict).
6. **Direct, no fluff, no marketing language**. Skip the kind of language a university recruiter would write. Prefer concrete details ("the first co-op begins in January of Year 1 — unusually early") over abstractions ("immersive co-op experience").

### Step 4 — Verification stamp

Add to the document header:

```
> **Research date**: <Month Year> | **Live-source verification**: <Month Year> (list of sources verified). Sources: <list>. All figures in CAD unless noted. Hourly-to-annual conversions assume 40 hrs/wk × 52 wks/yr = 2,080 hrs.
```

This signals to a future reader (or future you) when the numbers were last refreshed against the live sources.

### Step 5 — Bilingual pair (Chinese)

The repo convention pairs every English research doc with a Chinese (`-zh.md`) translation, and **the Chinese version is always produced** as part of this skill's standard output — do not ask first, do not stop after the English version. Once the English `<program>.md` is written and verified, immediately produce the matching `<program>-zh.md` translation following `references/translation-conventions.md`. The Chinese file should match the English line count within ±5%, preserve all citation links and table structures unchanged, and translate cell contents/prose using the established term mappings (universities, regulatory bodies, course codes preserved as-is). Mention to the user that both files have been written when reporting completion.

### Step 6 — Update README

After completing both the English and Chinese versions, update `README.md` to add the new doc to the **Comprehensive Research Reports** table at the top, with one row per program. Populate both the English and Chinese columns in the same edit.

## Output Format Quick Reference

The Quick Stats Table (Section 14) is the single best test of whether the rest of the document is complete. Every row should be filled. Use this skeleton:

```
| Metric | Value |
|---|---|
| Program length | X years |
| Co-op / internship: mandatory? | Yes / No |
| Co-op work terms / internship duration | X |
| Cohort size | X |
| % women in program | X% (year) or "Not publicly disclosed" |
| CEAB / accreditation | Yes — since YYYY |
| Competitive admission average | X% |
| Required Grade 12 prerequisites | list |
| Supplementary application | AIF / Casper / portfolio / interview / none |
| Annual tuition (domestic) | $X |
| Annual tuition (international) | $X |
| Total program cost (gross, domestic) | $X |
| Total program cost (net, after work earnings) | $X |
| Co-op / internship hourly Term 1 / final | $X / $X |
| Total co-op earnings (pre-tax) | $X |
| Graduate employment rate (6 mo or 2 yr) | X% |
| Entry-level salary (Ontario) | $X |
| Median wage (Ontario, NOC code) | $X/hr ≈ $X/yr |
| 90th percentile (Ontario) | $X/hr ≈ $X/yr |
| Senior salary range (10+ yrs) | $X |
| Professional license eligible? | Yes / No |
| License timeline post-grad | X years |
| Total HS → license timeline | X years |
| NOC outlook (Ontario, period) | Limited / Moderate / Good |
| Specialization tracks | list |
| Concurrent / dual degree options | list |
```

If a row reads "Not publicly disclosed" or is left blank, that is itself useful information — flag it explicitly rather than guessing.

## What NOT to Do

- **Don't make up numbers.** If a source doesn't have it, say so. Hedged honesty beats confident fiction.
- **Don't use marketing language.** "World-class," "innovative," "transformative" all signal a press release, not research.
- **Don't write a TL;DR that's optimistic by default.** The Three Things Most Applicants Get Wrong section exists specifically to balance the executive summary's necessary high-level framing.
- **Don't skip the realistic-probability analysis.** Even when a program has no obvious "filter" (like med school admission), the question "what fraction of admitted students reach each milestone" is still answerable in ranges, and matters to applicants.
- **Don't forget AI impact.** Every program should have an honest section on what AI is doing now in that field, what it can't do, and how the regulatory floor (or lack thereof) affects displacement risk.
- **Don't write the report from one source's perspective.** Triangulate. If Job Bank, Glassdoor, and student-reported data disagree, present the disagreement.
- **Don't stop after the English version.** Both English and Chinese (`-zh.md`) files are mandatory output. Producing only the English version is incomplete work for this skill.

## Reference Files

- `references/document-template.md` — Full annotated 15-section skeleton with examples from the anchor docs
- `references/source-allowlist.md` — Authoritative sources by program type (engineering vs. medicine vs. architecture vs. trades)
- `references/translation-conventions.md` — Patterns for the Chinese (`-zh.md`) translation pair

## Anchor Document (Read Before Writing a New One)

The first time this skill runs in a session, scan the section structure and voice of `mcmaster-life-sciences.md` (pre-medical pathway: medicine, dentistry, alternative health careers, MCAT/CASPer/MMI tactics, low-yield admission probabilities).

Match its voice and depth; take the section list from the template (Step 2). If the new program differs structurally (e.g., an engineering co-op program, or a graduate-entry professional school), adapt the year-by-year plan and professional pathway sections.
