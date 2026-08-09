# Data

Source: [CUAD v1](https://github.com/TheAtticusProject/cuad) (`data.zip`), 510 contracts, 41 clause categories.

Working file: `CUADv1.json` (SQuAD-style QA format — there is no `master_clauses.csv` in the CUAD download, despite that being a common assumption). Each contract has one QA item per category; a clause is present when the item's `answers` list is non-empty and `is_impossible` is `false`.

This project uses presence/absence per category (no raw PDF parsing or token-level span alignment needed for core scope) — see `notebooks/01_data_exploration.ipynb` for the extraction logic and the resulting per-category counts.

Core scope is limited to 10 of the 41 categories — see the README's Project Overview section for the list and rationale.
