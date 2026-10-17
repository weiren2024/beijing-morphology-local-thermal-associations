# Supplementary Data S8. Complete source data for joint thermal and coefficient comparisons

The data contain 4,005 analysed grid cells. `LID` identifies a grid and `RUN_ROWID` retains its model-run row identity. All observations and original zero values are retained. The model outputs are spatially dependent. These summaries describe their distribution and same-grid correspondence; they are not estimates of an intervention effect.

Figure 11 shows the complete within-morphology PWP–G1-coefficient joint counts. Figure 12 summarises the actual G1 and mean building height of the same eight cool/hot-tail intersections outlined in Figure 11e–h. Their precise conditions are retained in Table S8b and `PWP_extremes_betaG1_most_negative.csv`; Table S8e reports their original fit-class composition, and Table S8f reports sector-specific tail proportions.

## Variable and class definitions

`PWP_Day_total` is total-population-weighted summer daytime land-surface temperature in degrees Celsius. `G1_score` is the Min–Max-scaled green-quantity score, z(G_CA), derived from green class area and not converted to green-cover percentage. `BuildHeight_Mean` is mean building height in metres. `COEF_*` contains signed scaled local MGWR coefficients. The dependent and explanatory variables in that model were standardised to mean zero and standard deviation one. `LOCALR2` is the existing local model fit measure.

`LCZ_ZONE`: 1 = Compact, 2 = Open mid-/high-rise, 3 = Open low-rise, 4 = Green-space type. `LR2_ZONE`: 1 = lower fit, 2 = intermediate fit, 3 = higher fit. `PWP_within_morph_q` and `beta_G1_within_morph_q` are within-morphology quartiles defined in Table S8a. `sector` uses the fixed coordinate midpoints defined in Table S8c. The retained `lr2_bin` field is not used in this manuscript.

## Complete data

| File | Content |
| --- | --- |
| `joint_grid.csv` | All 4,005 paired grid records, original morphology and fit classes, projected coordinates, observed indicators, coefficients and descriptive labels. |
| `within_morph_quartile_thresholds.csv` | Unrounded PWP and G1-coefficient quartile thresholds for each morphology. |
| `PWP_betaG1_quartile_joint_counts.csv` | All 64 PWP-by-coefficient quartile cells. `row_percent` is 100 × joint count / the corresponding morphology-specific PWP-quartile count. Zero-count cells are retained. |
| `PWP_betaG1_quartile_joint_context.csv` | Actual G1, building height, PWP and G1-coefficient summaries for the same grid IDs in each of the 64 cells, with sector counts. Empty cells have n = 0 and missing distribution summaries. |
| `PWP_extremes_betaG1_most_negative.csv` | All eight cold/hot PWP-tail intersections with the lowest signed G1-coefficient quartile interval, including true denominators. |
| `PWP_extremes_betaG1_sector_counts.csv` | Geographic composition of the eight tail intersections across all four fixed sectors. |
| `paired_spearman.csv` | The complete predefined same-grid pairwise rank descriptions, including overall, morphology, fit-class and coordinate-sector summaries. No p values are supplied. |
| `PWP_all_eight_coefficients_spearman.csv` | Uniform PWP-to-coefficient rank descriptions for all eight indicators in the full sample and each morphology. |
| `eight_indicator_order_by_morphology.csv` | All coefficient and observed-indicator median values and class orders by morphology. |
| `eight_indicator_common_order_summary.csv` | Complete-order and endpoint comparisons under the same rules for all eight indicators. |
| `group_context.csv` | Actual G1, building height, PWP and coefficient summaries in all 12 original morphology-by-fit groups, retained as complete supporting group summaries. |
| `sector_context.csv` | Actual conditions in all 48 fixed-sector-by-morphology-by-fit groups, including every group count and distribution summary used in the geographic comparison. |
| `TableS8e_EN.csv` | Original fit-class counts and within-joint-set shares for all eight PWP-tail and coefficient-Q1 intersections. |
| `TableS8f_EN.csv` | Cool/hot-tail conditional proportions for all 16 morphology-by-sector combinations, with each numerator and denominator. |

## Reading distribution summaries

`q05`, `q25`, `median`, `q75` and `q95` are observed quantiles using linear interpolation. An IQR is q25–q75, and the central 90% interval is q05–q95. These intervals do not represent confidence intervals. `n` counts grid cells and does not assert statistical independence. Small groups are retained and flagged where relevant. In rank summaries, tied values receive average ranks; a constant input is marked undefined rather than set to zero.

The complete data retain all morphologies, all original local-fit classes and all eight explanatory indicators. Counts and percentages are descriptive. The coefficients and significance flags in the joint-grid source come from the main MGWR output.


Field units, quartile intervals, denominators and missing-value conventions are defined in `Data_dictionary_EN.md`. Component formulas and indicator-selection records are supplied in `Indicator_definitions_EN.md`.
