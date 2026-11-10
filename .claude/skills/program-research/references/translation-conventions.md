# Translation Conventions — English ↔ Chinese (`-zh.md`)

The repo pairs every comprehensive research report in English with a Chinese translation suffixed `-zh.md`. The translation should match line count and structure within ~5%; if the English version is 1,800 lines, the Chinese version should land in 1,710–1,890 lines.

## Workflow

1. **Always produce the Chinese version automatically.** It is not optional and not a follow-up question — the `-zh.md` file is mandatory output of the `program-research` skill, written immediately after the English version is verified. Do not ask the user; do not stop after the English file.
2. Match section structure, table structure, and citation links exactly. Do not rewrite or reorganize — translate.
3. Verify line count after writing. Significant divergence (more than 10%) usually means a section was lost or the table-row count changed. Aim for ±5% match against the English file.
4. After both files exist, update `README.md` to populate **both** the English and Chinese columns in the Comprehensive Research Reports table — never leave the Chinese cell as "pending."

## Header Conventions

The English header:

```markdown
# University of Waterloo — Architectural Engineering (BASc Co-op)
## Comprehensive Research Report: P.Eng. Pathway, Building Industry Outlook & Career Strategy | May 2026

> **Research date**: May 2026 | **Live-source verification**: May 2026 (...)
```

Becomes:

```markdown
# 滑铁卢大学 (University of Waterloo) — 建筑工程 (Architectural Engineering, BASc Co-op)
## 综合研究报告：P.Eng. 执照路径、建筑行业前景与职业策略 | 2026年5月

> **研究日期**：2026年5月 | **现场来源核验日期**：2026年5月（...）
```

Key rules:
- Universities and program names: **Chinese first, English in parentheses**. This makes the doc accessible to Chinese readers who recognize the program by Chinese name first, while preserving the canonical English term for cross-reference.
- Dates: **2026年5月** (year-month-day in Chinese order)
- Section title: "综合研究报告" + colon + descriptor

## Term Mappings

### Universities and Programs

| English | Chinese (first mention) | Subsequent |
|---|---|---|
| University of Waterloo | 滑铁卢大学 (University of Waterloo) | 滑铁卢 / UW |
| Western University | 西安大略大学 (Western University) | 西安大略 / Western |
| McMaster University | 麦克马斯特大学 (McMaster University) | 麦克马斯特 / McMaster |
| University of Toronto | 多伦多大学 (University of Toronto) | 多伦多大学 / U of T |
| Architectural Engineering | 建筑工程 (Architectural Engineering) | 建筑工程 / ArchE |
| Electrical Engineering | 电气工程 (Electrical Engineering) | 电气工程 / EE |
| Civil Engineering | 土木工程 (Civil Engineering) | 土木工程 |
| Honours Life Sciences | 荣誉生命科学 (Honours Life Sciences) | 生命科学 |
| Architecture (BAS+MArch) | 建筑学 (BAS+MArch) | 建筑学 |
| Bachelor of Applied Science | 应用理学学士 (Bachelor of Applied Science, BASc) | BASc |
| Bachelor of Engineering Science | 工程科学学士 (Bachelor of Engineering Science, BESc) | BESc |
| Master of Architecture | 建筑学硕士 (Master of Architecture, MArch) | MArch |
| Honors Business Administration | 荣誉工商管理学士 (Honors Business Administration, HBA) | HBA |

### Faculties and Departments

| English | Chinese |
|---|---|
| Faculty of Engineering | 工程学院 |
| Faculty of Science | 理学院 |
| School of Architecture | 建筑学院 |
| Department of Civil & Environmental Engineering | 土木与环境工程系 |
| Department of Electrical and Computer Engineering | 电气与计算机工程系 |
| School of Interdisciplinary Science | 跨学科科学学院 |

### Regulatory Bodies and Credentials

| English | Chinese (keep English acronym) |
|---|---|
| PEO (Professional Engineers Ontario) | 安大略省专业工程师协会 (PEO) |
| OAA (Ontario Association of Architects) | 安大略省建筑师协会 (OAA) |
| CEAB (Canadian Engineering Accreditation Board) | CEAB（加拿大工程认证委员会） |
| Engineers Canada | 加拿大工程师协会 (Engineers Canada) |
| P.Eng. | P.Eng.（保留原文） |
| EIT (Engineering Intern) | 工程实习生 (EIT) |
| NPPE | NPPE（保留原文） |
| CBA (Competency-Based Assessment) | 能力评估 (CBA) |
| LEED AP | LEED AP（保留原文） |
| WELL AP | WELL AP（保留原文） |
| AIF (Admission Information Form) | 入学信息表 (Admission Information Form, AIF) |

### Government and Statistics

| English | Chinese |
|---|---|
| Statistics Canada | 加拿大统计局 (Statistics Canada) |
| Job Bank | Job Bank（保留原文，可加"加拿大就业银行"前缀首次出现）|
| NOC (National Occupational Classification) | 国家职业分类 (NOC) |
| OSAP | OSAP（保留原文） |
| BuildForce Canada | BuildForce Canada（保留原文） |
| CAGBC | CAGBC（保留原文，"加拿大绿色建筑委员会"首次出现） |

### Industry and Job Terms

| English | Chinese |
|---|---|
| Co-op / Internship | Co-op / 实习 |
| Capstone | 毕业设计 / Capstone |
| Year-Long Co-op | Year-Long Co-op / 年度 Co-op |
| Common First Year | 公共第一年 (Common First Year, CFY) |
| Engineering Excellence | Engineering Excellence（保留原文，首次加"工程卓越"） |
| AEC (Architecture/Engineering/Construction) | AEC（建筑、工程、施工） |
| BIM | BIM（保留原文） |
| HVAC | HVAC（保留原文） |
| MEP (Mechanical, Electrical, Plumbing) | MEP（机械、电气、给排水） |
| Net-zero | 净零碳 / 净零 |

## Cities

| English | Chinese |
|---|---|
| Toronto | 多伦多 |
| Waterloo | 滑铁卢 |
| Cambridge (Ontario) | 剑桥 (Cambridge, ON) |
| Kitchener-Waterloo | 基奇纳-滑铁卢 |
| London (Ontario) | 伦敦 (London, ON) |
| Ottawa | 渥太华 |
| Vancouver | 温哥华 |
| Calgary | 卡尔加里 |
| Hamilton | 汉密尔顿 |
| Montreal | 蒙特利尔 |
| Halifax | 哈利法克斯 |
| Sarnia | 萨尼亚 |

## Numbers and Units

- Keep dollar amounts as `$X` — Canadian dollars are the default. Use `$X 美元` only when explicitly USD.
- Hours: `X 小时` or `X 小时/周`
- Hourly rates: `$X/小时`
- Annual rates: `$X/年`
- Percentages: `X%`
- Year ranges: `2025–2027`
- Numbers under 10,000: keep digit form (`5,000`)
- Numbers 10,000+: prefer Chinese counters (`27 万`, `380,500`) — use the form most natural in context
- Salary range bands (e.g., "$120K–$180K"): keep K notation
- Total income figures (millions in 25-year analysis): use `$300万` style for readability

## Voice and Style in Translation

- **Preserve hedging language** — "hedged caveat" → "对冲说明"; "the source does not break out X" → "来源不分解 X"; "treat as approximate" → "视为大致估算".
- **Preserve "what this means for you" sections** — translate to "对申请者的实务含义" or "实务含义" or "对未来学生的实务含义".
- **Bottom-line callouts** in italicized blockquotes — keep the blockquote `>` and italics `*...*` formatting.
- **Worked examples** — translate the math but keep number formats. The example "Term 1: $21.67 × 640 hr = $13,869" becomes "第 1 学期：$21.67 × 640 小时 = $13,869".
- **Citations** — keep the inline `[domain](URL)` format unchanged. Translate any descriptive text around the citation but leave the link untouched.
- **Tables** — preserve column count, row count, and pipe alignment. Translate cell contents.

## Common Pitfalls

1. **Forgetting to translate the Table of Contents.** TOC entries must match the section headers — translate both together. Verify the TOC anchors match section IDs.
2. **Section header anchors.** Markdown auto-generates anchors from headers. Chinese headers create different anchors than English. The `#` linking in the TOC must use the Chinese-anchor form.
3. **Inline acronyms losing context.** "P.Eng." appears 60+ times in a typical document. Don't try to translate it each time; first mention can have "专业工程师 (P.Eng.)" but subsequent uses are just "P.Eng.".
4. **Skipping the verification line in the header.** The "Live-source verification" line must be translated, not omitted.
5. **Length mismatch.** If the Chinese version is 200+ lines shorter than the English, a section is missing. Re-read against the English version.

## Footer

End the Chinese version with:

```
*研究编纂于 [年 月]。除特别说明外，数据来自 [年份范围] 年来源。除特别说明外，薪资数据为加元。时薪折算年薪假设为 40 小时/周 × 52 周/年 = 2,080 小时（Job Bank 不公布年化数字）。所有声明都链接到公开可用的权威来源，或在没有公开来源时附明确方法论说明的对冲。*
```

## After Writing the Translation

1. **Verify line count is within ±5–10%** of the English version.
2. **Verify section count matches** (15 sections + sub-sections).
3. **Spot-check 3–5 numerical claims** against the English version — they should be byte-identical.
4. **Update README.md** to add the Chinese row to the Comprehensive Research Reports table.
