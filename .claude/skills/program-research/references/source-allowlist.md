# Source Allowlist — Authoritative Sources by Program Type

The repo's `.claude/settings.local.json` allowlists specific domains for WebFetch. Use these for primary verification; treat anything outside the allowlist as directional only and flag it explicitly.

## Universal — Use for All Programs

| Source | URL Pattern | What to Verify |
|---|---|---|
| **Job Bank wages** | `jobbank.gc.ca/marketreport/wages-occupation/<NOC>/ON` | Low/Median/90th-percentile hourly wages, Toronto sub-median, benefit coverage rate, wage update date |
| **Job Bank outlook** | `jobbank.gc.ca/marketreport/outlook-occupation/<NOC>/ON` | Limited / Moderate / Good rating, period covered, demand drivers, headwinds, outlook update date |

**Common NOC codes:**
- 21300 Civil engineers (used as proxy for Architectural Engineering, building structural / MEP P.Eng.)
- 21301 Mechanical engineers
- 21310 Electrical and electronics engineers
- 21311 Computer engineers (excluding software)
- 21320 Chemical engineers
- 21200 Architects
- 21100 Statisticians (relevant for biostatistics pivots)
- 30010 Specialist physicians
- 31100 Family physicians
- 31110 Dentists
- 31112 Pharmacists
- 31202 Optometrists

## Engineering Programs (CEAB-accredited)

### University-Specific

| Source | URL | Use For |
|---|---|---|
| **UWaterloo program pages** | `uwaterloo.ca/future-students/programs/<program>` | Prerequisites, admission averages, AIF, supplementary requirements |
| **UWaterloo engineering pages** | `uwaterloo.ca/engineering/future-students/<program>` | Faculty-level program details, cohort statistics, women's enrollment |
| **UWaterloo co-op earnings** | `uwaterloo.ca/hire/how-to-hire/co-op-student-earnings` | Term-by-term hourly wage averages (refreshed annually) |
| **UWaterloo study/work sequences** | `uwaterloo.ca/future-students/co-op/study-work-sequences` | Stream sequences (4S, 8S, etc.) |
| **UWaterloo KPI report** | `uwaterloo.ca/institutional-analysis-planning/key-performance-indicators-university-waterloo-<year>` | Faculty employment rates, retention, graduation |
| **UWaterloo Imprint** | `uwimprint.ca/...` | Co-op employment rate corroboration |
| **UWaterloo fee schedule** | `uwaterloo.ca/finance/fee-schedule-domestic-ontario-undergraduates-fall-<year>` | Tuition, ancillary fees, co-op fees |
| **UWaterloo tuition summary** | `uwaterloo.ca/future-students/financing/tuition` | First-year all-in tuition summary |
| **Western program pages** | `eng.uwo.ca/<dept>/...` | Specializations, progression sheets, dual degrees |
| **Western admission** | `eng.uwo.ca/undergraduate/first-year/admission_to_programs.html` | Year 1 → Year 2 sort criteria, common first year |
| **Western Engineering Excellence** | `eng.uwo.ca/future-students/your-eng-experience/first-year/engineering-excellence.html` | 85% threshold for guaranteed Year-2 program |
| **Western co-op / internship** | `eng.uwo.ca/careers/students/...` | Internship program, average $50K Year-Long Co-op |
| **Western admission requirements** | `welcome.uwo.ca/next-steps/requirements/ontario-high-school.html` | Casper requirement, Grade 12 prerequisites |
| **Western fee schedule** | `registrar.uwo.ca/student_finances/fees_refunds/...` | Engineering tuition and ancillary fees |
| **Western residence** | `residence.uwo.ca/applying/fees_and_payment` | Residence fees by hall type, meal plan |

**Note on PDFs:** Western publishes program progression sheets and fee schedules as PDFs. WebFetch on these often fails to parse binary content. Fall back to citing the PDF URL with the comparison-doc figure as a triangulation.

### Engineering Licensing

| Source | URL | Use For |
|---|---|---|
| **PEO licensing pathway** | `peo.on.ca/apply/become-professional-engineer` | 48-month experience requirement, NPPE, 12-month co-op credit |
| **PEO CEAB graduates** | `peo.on.ca/licence-applications/become-professional-engineer/graduates-ceab-accredited-engineering-program` | Academic requirement automatic for CEAB |
| **PEO Competency-Based Assessment** | `peo.on.ca/licence-applications/become-professional-engineer/competency-based-assessment` | 7 competency categories, validator requirements |
| **Engineers Canada accreditation** | `engineerscanada.ca/accreditation/accredited-programs/institution?page=<N>` | CEAB accreditation year, current status |

## Architecture Programs

| Source | URL Pattern | Use For |
|---|---|---|
| **OAA (Ontario Association of Architects)** | `oaa.on.ca` | IAP, ExAC, OAA Admission Course, licensing pathway |
| **CACB** | `cacb-ccca.ca` | Architecture program accreditation |
| **RAIC** | `raic.org` | National professional architects body |
| **UW School of Architecture** | `uwaterloo.ca/architecture` | BAS + MArch program details |

## Medical / Pre-Medical Pathways

| Source | URL Pattern | Use For |
|---|---|---|
| **OMSAS** | `ouac.on.ca/omsas` | Application timeline, fees, deadlines. Returns 403 to WebFetch; verify via authoritative search results and say so in the report |
| **AAMC (MCAT)** | `aamc.org/services/mcat` | MCAT format, content, scoring |
| **CASPer / Acuity Insights** | `acuityinsights.com` | CASPer test format, free practice |
| **AFMC** | `afmc.ca` | Canadian Medical Education Statistics (applicants, matriculants, acceptance rates) |
| **CaRMS** | `carms.ca` | Residency match results by discipline |
| **PARO** | `myparo.ca/financial-primer/` | Ontario resident (PGY) salary scale; the HTML page parses, the PDF does not |
| **Ontario MD programs** | `ugme.healthsci.mcmaster.ca`, `applymd.utoronto.ca`, `schulich.uwo.ca`, `meds.queensu.ca`, `uottawa.ca` (Faculty of Medicine pages), `nosm.ca`, `torontomu.ca`, `yorku.ca/medicine` | School-specific admission rules and stats. Not all are on the WebFetch allowlist — ask the user before adding a domain. uOttawa blocks WebFetch; use the browser |
| **McMaster registrar / housing** | `registrar.mcmaster.ca`, `housing.mcmaster.ca` | Tuition and residence fees |
| **Statistics Canada** | `statcan.gc.ca` | Population-level earnings and education data |

## Construction / Building Industry

| Source | URL | Use For |
|---|---|---|
| **BuildForce Canada** | `buildforce.ca/en/press-release/...` | National construction labour forecast, retirement projections, Ontario-specific data |
| **CAGBC** | `cagbc.org/news-resources/cagbc-news/...` | Green building jobs forecast, LEED data |
| **NRCan Green Buildings** | `natural-resources.canada.ca/energy-efficiency/building-energy-efficiency/canada-green-buildings-strategy` | Federal net-zero strategy, annual investment projections |
| **On-Site Magazine** | `on-sitemag.com/features/...` | Construction industry forecasts |

## Salary Triangulation Sources

Use these alongside Job Bank for cross-checking; not allowlisted as primary but acceptable for triangulation:

| Source | What to Watch For |
|---|---|
| Glassdoor Canada | User-reported salaries; can be skewed by selection bias |
| ZipRecruiter | Aggregated postings; skews toward lower entry rates |
| SalaryExpert | Modeled estimates; treat as directional only |
| Levels.fyi | Tech-specific total compensation; high accuracy for FAANG / equity |

## AI Impact

| Source | What to Cite |
|---|---|
| **Anthropic Economic Index v4 (Jan 2026)** | Figures for the SOC group that matches the program (e.g., Healthcare Practitioners for pre-med). Do not reuse another group's figures. Example, Architecture and Engineering: 38% automation / 59% augmentation / ~12× speedup / ~66% college-level success rate. Access via local NotebookLM workflow (URL in repo settings). |
| **Autodesk Construction AI** | `autodesk.com/blogs/construction/2026-ai-trends...` for industry adoption signals |

## Hedged or Non-Allowlist Sources

Numbeo, Reddit, MacInsiders, premed101, and similar crowd-sourced or forum sources can provide directional context but should always be flagged as such:

> *(non-allowlist source — Numbeo cost-of-living data is crowdsourced and used as directional only; not a primary authoritative source per spec.)*

## What to Verify, by Program Type

### Engineering (mandatory for any Eng. report)
- CEAB accreditation year and current status (Engineers Canada)
- Tuition and fees (university registrar)
- Co-op / internship structure and pay (faculty co-op page)
- NOC code wages and outlook (Job Bank)
- PEO 48-month experience requirement and co-op credit (PEO)
- Faculty employment rate (KPI report)

### Pre-Medical (mandatory for any Med-track report)
- McMaster MD or relevant school admission stats (school MD page)
- MCAT format and CARS-only weighting where applicable (AAMC, school)
- CASPer requirement and weight (Acuity Insights, school)
- OMSAS timeline (OUAC OMSAS)
- Applicant and acceptance statistics (AFMC)
- Resident salary scale (PARO) and match outcomes (CaRMS)
- Tuition and total cost (university registrar)

### Architecture (mandatory for any Architecture report)
- CACB accreditation
- OAA IAP and ExAC pass rates
- Co-op structure (school co-op office)
- Tuition (university registrar)
- Job Bank NOC 21200 wages and outlook
- BAS+MArch program structure

## Re-Verification Cadence

Job Bank wages refresh roughly twice per year. Outlook ratings update with similar cadence (often December). University tuition refreshes annually each Fall. CEAB accreditation listings update less often. Re-verify before producing a new report or whenever an existing report is older than 6 months.
