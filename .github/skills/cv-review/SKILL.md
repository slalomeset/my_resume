---
name: cv-review
description: Review and improve the primary LaTeX resume without changing established facts.
---

# CV Review

Use this skill for recruitment-oriented review or editing of either resume source:

- `short/vladimir_sirghi_short.tex`
- `detailed/vladimir_sirghi_detailed.tex`

## Workflow

1. Read the requested source and identify the target role or job description.
   For an offer-specific resume, default to the short source unless the user
   requests the detailed version; otherwise ask which version to edit if unclear.
2. Assess factual accuracy, chronology, ATS compatibility, role relevance, recruiter readability, and LaTeX stability.
3. For review-only requests, report findings as:
   - Executive summary
   - Priority findings
   - Suggested revisions
   - Questions needed to verify impact
4. For editing requests, make surgical changes directly in the LaTeX source.
5. Build with the matching `Build Short Resume` or `Build Detailed Resume` task.
6. Report changed files, build status, warnings, page count, and remaining decisions.

For an offer-specific resume, save the tailored copy to
`cover_letter/applications/<company>-<role>/resume.tex`, record supporting
evidence in that application's `evidence.md`, and leave both canonical sources
unchanged. Build the tailored copy with `latexmk -pdf resume.tex` from its
application directory.

## Rules

- Preserve established facts unless the user provides corrections or additions.
- Never invent employers, dates, degrees, certifications, technologies, metrics, or achievements.
- Use verified metrics only.
- Preserve existing LaTeX macros and special-character escaping.
- Keep normal, ATS-readable headings and text.
- Do not edit the generated PDF directly.
- Do not expose or add sensitive personal information without explicit consent.
