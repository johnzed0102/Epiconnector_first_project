1. Use jointQuery() to simplify joins and let the database handle merging across cycles.
2. Use |> instead of %>% to minimize tidyverse dependencies.
3. Quick Start file, line 224: defines cols <- list(...) and uses jointQuery(cols); this is the key example to follow.
4. Don’t select columns by numeric index; always use variable names.
5. Don’t keep unused variables; only retain what’s required for analysis.
6. Avoid heavy tidyverse usage; some dplyr may appear but usually results are converted back to data.frames quickly.
7. Line 180 is not replicating the textbook correctly; revise to match.
8. BPXSAR/BPXDAR: confirm whether your manually computed values match the pre-calculated ones in the NHANES database.
9. Survey design options: try options(survey.lonely.psu = "adjust") when creating svydesign().
10. Investigate differences between your desktop environment (nhanesA) and container environment (phonto/DB).
11. Interaction modeling:
      - Try interaction between age and sex.
      - Try natural splines for age and interact with sex (ns(RIDAGEYR,5) * RIAGENDR).
12. Tables: produce them directly from model objects to avoid transcription errors.
