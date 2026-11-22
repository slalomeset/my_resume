---
name: cover-letter
description: Generate a fact-grounded LaTeX cover letter and, when requested, a tailored resume for a job offer.
---

# Job Application

Use this skill to create or revise a cover letter, an offer-specific resume, or
both for a specific job offer.

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
   - source file and section;
   - confidence level;
   - missing information.
3. Confirm which deliverable(s) the user wants if unclear.
4. For a letter, generate an outline before prose:
   - why this role;
   - why this company;
   - 2-3 strongest matching qualifications;
   - role-specific contribution;
   - concise closing.
5. For a tailored resume, use the short source as the starting point, consult the
   detailed source only for verified supporting facts, and write the offer-specific
   copy to `cover_letter/applications/<company>-<role>/resume.tex`. Never replace
   either canonical resume source.
6. Mark facts that cannot be verified; do not add them to a deliverable.
7. Compile each requested LaTeX source in the application directory and inspect
   warnings, page count, layout, and searchable text.
8. Report source files used, output status, evidence gaps, and required user decisions.

## Factuality rules

- Never invent employers, dates, degrees, certifications, metrics, achievements, products, or technologies.
- Never present an inference, estimate, or plausible wording as a verified fact.
- Never imply that a tool, responsibility, or result belongs to the candidate when only the offer or a current external status contains it.
- Prefer an omission over an unsupported claim.
- Report missing company, recruiter, address, or application details as questions rather than guessing.
- Use only the explicit language or market form when personal language preference is unknown.

## Resume and letter quality

- Tailor relevance, ordering, summary, skills, and bullet selection naturally.
- Keep resume claims traceable to their source in `evidence.md`.
- Do not add offer keywords, responsibilities, or claims without supporting evidence.
- Preserve the candidate's personal-information consent choices.
- When copying the resume source, set its photo path to
  `../../../ressources/photo/cv_photo.jpg` for a build from the application
  directory without changing the canonical source.

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
- For a cover letter, use the existing `letter` document pattern unless a
  stronger template is requested.
- Keep links accessible and avoid layout-heavy content.
- Compile after every substantive LaTeX edit.
- Use `latexmk -pdf letter.tex` and/or `latexmk -pdf resume.tex` in the application directory, as requested.
