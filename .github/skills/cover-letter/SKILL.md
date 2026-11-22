---
name: cover-letter
description: Generate a fact-grounded LaTeX cover letter from a job offer and the primary resume.
---

# Cover Letter

Use this skill to create or revise a cover letter for a specific job offer.

## Source of truth

- Read `short/vladimir_sirghi_short.tex` and `detailed/vladimir_sirghi_detailed.tex` for established experience, education, tools, industries, and chronology.
- Read the supplied offer text from `offer.txt` or an explicitly selected text file.
- Read `cover_letter/cover_letter_template.tex` for the reusable LaTeX structure.
- Consult `/home/vlad/repos/week_status` only when the user explicitly asks or when the offer requires a current achievement that is not yet in the resume.
- Use established evidence from the resume sources before using `week_status`, and record which source supports each claim.

## Workflow

1. Read the offer and extract:
   - company and team;
   - position title;
   - responsibilities;
   - required and preferred skills;
   - location and language;
   - explicit or implicit selection criteria.
2. Read the resume and build an evidence table:
   - offer requirement;
   - matching resume evidence;
   - source line or section;
   - confidence level;
   - missing information.
3. Generate an outline before prose:
   - why this role;
   - why this company;
   - 2-3 strongest matching qualifications;
   - role-specific contribution;
   - concise closing.
4. Draft `letter.tex` in the requested language and target the offer naturally.
5. Mark facts that cannot be verified, but do not add them to the letter.
6. Compile with `latexmk -pdf letter.tex`.
7. Report source files used, output status, evidence gaps, and any required user decisions.

## Factuality rules

- Never invent employers, dates, degrees, certifications, metrics, achievements, products, or technologies.
- Never present an inference, estimate, or plausible wording as a verified fact.
- Never imply that a tool, responsibility, or result belongs to the candidate when only the offer or a current external status contains it.
- Prefer an omission over an unsupported claim.
- Report missing company, recruiter, address, or application details as questions rather than guessing.
- Use only the explicit language or market form when personal language preference is unknown.

## Letter quality

- Keep the letter concise, typically one page.
- Use 2-3 concrete evidence-based examples; avoid restating the entire resume.
- Connect the candidate's established experience to the offer's priorities.
- Avoid generic phrases, exaggerated enthusiasm, and ATS keyword stuffing.
- Preserve the candidate's seniority and professional tone.
- Do not copy full sentences or paragraphs from the offer.
- Escalate only facts not found in the sources; do not ask for details that are already in the resume.

## LaTeX rules

- Preserve valid escaping and LaTeX special characters.
- Do not edit the generated PDF directly.
- Use the existing `letter` document pattern unless a stronger template is requested.
- Keep links accessible and avoid layout-heavy content.
- Compile after every substantive LaTeX edit.
- Use `latexmk -pdf letter.tex` in the application directory.
