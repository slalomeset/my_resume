# Job application workflow

The `job_application_writer` agent creates a fact-grounded, offer-specific resume,
cover letter, or both from a job offer and the canonical resume sources.

## Create an application

1. Copy `offer_template.txt` into:

   ```text
   cover_letter/applications/<company>-<role>/offer.txt
   ```

2. Paste the job offer and fill in the metadata fields.
3. Select the `job_application_writer` agent in Copilot Chat.
4. Ask for a tailored short resume, a cover letter, or both.
5. Review `evidence.md` and the generated source files before using them.

## Output

Each application is kept in its own directory:

```text
cover_letter/applications/<company>-<role>/
  offer.txt
  evidence.md
  resume.tex       # created when requested
  resume.pdf       # generated when resume.tex is created
  letter.tex       # created when requested
  letter.pdf       # generated when letter.tex is created
```

The application-specific `resume.tex` is derived from the short resume; the
detailed resume may be used to verify supporting facts. Neither canonical resume
source is changed. The `letter.tex` and `resume.tex` files are editable sources;
their PDFs are generated artifacts. Only create the deliverables requested.

## Validation

Run the relevant command inside the application directory:

```bash
latexmk -pdf letter.tex
latexmk -pdf resume.tex
```

When creating `resume.tex`, set the photo path to
`../../../ressources/photo/cv_photo.jpg` when building from the application
directory. Inspect the PDF for LaTeX warnings, page count, layout, and searchable
text before sharing it.
