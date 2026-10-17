# Supplementary Data S9. Existing-output comparison of thermal-tail overlaps

The comparison uses the same 4,005 analysis units and the two existing MGWR outputs with neighbourhood-search lower bounds of 1,400 and 1,600. The main-text model remains the 1,600 output.

| File | Content |
| --- | --- |
| `tail_comparison.csv` | Eight cool/hot-tail overlap counts, fixed denominators, percentages and between-run percentage-point changes; Table S9a. |
| `direction_comparison.csv` | Hot-minus-cool percentage-point differences for each morphology in both outputs. |
| `member_change_summary.csv` | Complete Q1 membership counts, entries and exits by morphology; Table S9b. |
| `run_quartile_thresholds.csv` | Unrounded PWP and signed G1-coefficient quartile thresholds for all morphologies and both runs. |
| `full_joint_counts.csv` | All 128 morphology-by-PWP-quartile-by-coefficient-quartile cells across both outputs, including zero counts. |
| `member_comparison_4005.csv` | Grid identities, PWP and coefficient quartile labels, both G1 coefficients, and Q1 membership-change flags for all 4,005 grids. |

The coefficients use the software-standardised model (mean zero and standard deviation one), not original-unit temperature slopes. PWP quartile memberships are fixed and each run's coefficient quartile memberships are calculated separately within morphology. The same tie and interval rules as Table S8a apply. Both runs use the same response and explanatory variables; the comparison describes changes between the two neighbourhood lower bounds.


Field units, quartile intervals, denominators and missing-value conventions are defined in `Data_dictionary_EN.md`. Component formulas and indicator-selection records are supplied in `Indicator_definitions_EN.md`.
