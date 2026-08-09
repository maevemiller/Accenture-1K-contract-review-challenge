# Data

Source: [CUAD v1](https://github.com/TheAtticusProject/cuad) (`data.zip`), 510 contracts, 41 clause categories.

Working file: `CUADv1.json` (SQuAD-style QA format; there is no `master_clauses.csv` in the download). Each contract has one QA item per category; a clause is present when the item's `answers` list is non-empty and `is_impossible` is `false`.

Detection uses presence/absence per category — see `notebooks/01_data_exploration.ipynb` for the extraction logic and the resulting per-category counts.

Core scope is limited to 10 of the 41 categories — see the README's Project Overview section for the list.
