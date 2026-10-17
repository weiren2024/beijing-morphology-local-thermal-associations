# Supplementary Data S6

The two CSV files contain the existing cross-classified summaries for four urban morphology types, three local-fit classes and eight indicators, giving 96 rows per file. Each row represents one morphology–fit-class–indicator combination. They support Tables S6a–b and Figures 9–10.

- `TableS6a_indicator_rank_and_raw_profiles.csv` contains the indicator's centred within-morphology percentile ranks and its model-input values.
- `TableS6b_scaled_coefficient_profiles.csv` contains signed local coefficients from the standardised MGWR and the associated software significance flags.

`morphology_id` is 1 = Compact, 2 = Open mid-/high-rise, 3 = Open low-rise and 4 = Green-space type. `fit_class` is 1 = lower, 2 = intermediate and 3 = higher Local R². `n` counts grid cells in the group. `variable` identifies the indicator.

In the first file, `mean`, `sd`, `min`, `q05`, `q25`, `median`, `q75`, `q95` and `max` describe centred percentile ranks, d = 2(q − 0.5), with average ranks for ties and all grids of the relevant morphology as the reference population. The corresponding `raw_` fields describe unranked model-input values, with the unit recorded in `raw_unit`. Canopy height is reported in metres in these tables.

In the second file, the same summary suffixes describe signed standardised-model coefficients. `native_significant_share_pct` is the percentage of grid cells carrying the software-corrected significance flag. `negative_share_pct` and `positive_share_pct` describe coefficient signs. The two `native_significant_*_share_pct` fields count grid cells satisfying both the significance and indicated sign condition, as a percentage of all grid cells in the row's group.

Quantiles describe observed distributions, not confidence intervals. Blank values denote unavailable summaries rather than zero. Variable definitions are given in main-text Table 2 and Supplementary Table S1; the indicators and coefficients use different scales.


Field units, quartile intervals, denominators and missing-value conventions are defined in `Data_dictionary_EN.md`. Component formulas and indicator-selection records are supplied in `Indicator_definitions_EN.md`.
