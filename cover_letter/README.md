# Cover letter workflow

The `job_application_writer` agent generates a tailored, fact-grounded cover letter
from a job offer and the primary LaTeX resume.

## Create an application

1. Copy `offer_template.txt` into:

   ```text
   cover_letter/applications/<company>-<role>/offer.txt
   ```

2. Paste the job offer and fill in the metadata fields.
3. Select the `job_application_writer` agent in Copilot Chat.
4. Ask: “Create a cover letter for this offer.”
5. Review `evidence.md` before finalizing the letter.

## Output

Each application is kept in its own directory:

```text
cover_letter/applications/<company>-<role>/
  offer.txt
  evidence.md
  letter.tex
  letter.pdf
```

The `letter.tex` file is the editable source. The PDF is a generated artifact.

## Validation

Run the following inside the application directory:

```bash
latexmk -pdf letter.tex
```
