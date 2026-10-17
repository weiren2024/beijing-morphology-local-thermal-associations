# Supplementary data dictionary

This dictionary defines the fields, units, classifications and denominators in Supplementary Data S6, S8 and S9.

## Files and units of observation

Data S6 contains two 96-row files, one row per urban morphology type × local-fit class × indicator. Its `Data_guide.md` defines relative ranks, raw-value summaries and coefficient summaries. Data S8 contains 14 CSV files and a data guide: one complete 4,005-grid joined table plus cross-tabulations, distribution summaries, coefficient-order comparisons and spatial-sector descriptions. Data S9 contains six CSV files and a data guide comparing the two existing neighbourhood-search lower bounds, 1,400 and 1,600. The main manuscript uses the 1,600 output.

The complete file-by-file contents are listed in each data folder's `Data_guide.md`. `field_inventory.csv` lists every CSV field and the files in which it occurs; the definitions below apply to families of fields as well as individual fields.

## Grid identities and observed variables

| Field or family | Definition and unit |
| --- | --- |
| `LID` | Stable analysis-grid identifier. |
| `RUN_ROWID` | Row identifier retained from the model run. |
| `Centroid_X`, `Centroid_Y` | Grid-centroid projected coordinates in metres, EPSG:32650. |
| `PWP_Day_total`, `PWP` | Total-population-weighted summer daytime land-surface temperature, °C. |
| `BuildHeight_Mean` | Mean height over building-covered areas, m. |
| `CanopyHeight_Mean` in `joint_grid.csv` | Original model-input canopy-height field, in cm; the supplementary display tables report its equivalent in m. Valid zero heights are retained. |
| `G1_score` | Min–Max-scaled green class area, dimensionless green-quantity score; not green-cover percentage. |
| `G2_score` | Green fragmentation–extension score, with the component formula and aggregation rule in Table S1. |
| `G3_score`, `B3_score` | Green and grey connectivity–interspersion scores, respectively, with definitions in Table S1. |
| `GBRDG_Pct`, `BBRDG_Pct` | Green and grey Bridge area as a percentage of the corresponding MSPA foreground area. |

## Model outputs and classifications

| Field or family | Definition |
| --- | --- |
| `LOCALR2`, `LocalR2_*` | Existing MGWR local goodness of fit or its group summaries. |
| `COEF_*`, `beta_G1*`, `beta_height*` | Signed local coefficients or their summaries from the model with Y and X standardised to mean zero and standard deviation one. They are not temperature slopes in original units. |
| `G1_coefficient_1400`, `G1_coefficient_1600` | Existing signed G1 coefficients from the two neighbourhood-search lower-bound settings. |
| `SIG_*` | Existing software-corrected significance flag: 1 indicates flagged significance and 0 indicates no flag. |
| `RANKDEV_*` | Centred within-morphology percentile ranks, d = 2(q − 0.5), with average ranks for ties. |
| `LCZ_ZONE`, `morphology`, `morphology_id`, `morphology_code` | Morphology code when numeric: 1 = Compact, 2 = Open mid-/high-rise, 3 = Open low-rise, 4 = Green-space type. Textual `morphology` and `morphology_label`/`morph_label` fields give the corresponding labels. These are the study's aggregated morphology types. |
| `LR2_ZONE`, `fit_class` | Existing local-fit classes: 1 = lower, 2 = intermediate, 3 = higher. Exact boundaries are in Table S4. `fit_label` is their text label. |
| `lr2_bin` | Retained ancillary field; not used in the manuscript's three-class comparisons. |
| `sector` | NW, NE, SW or SE, based on the fixed full-sample centroid bounding-box midpoints X = 458874.0841 m and Y = 4413648.5752 m. Equality goes to east or north. |
| `run_lower_bound` | Neighbourhood-search lower bound identifying an existing model output: 1,400 or 1,600. |

## Quartiles and denominators

`PWP_within_morph_q`, `PWP_quartile` and `PWP_tail` identify the PWP quartile interval or cool/hot tail. `beta_G1_within_morph_q`, `beta_G1_quartile`, `beta_quartile` and their run-suffixed variants identify the signed G1-coefficient quartile interval. Each variable is partitioned separately within each morphology: Q1 ≤ q25, Q2 = (q25, q50], Q3 = (q50, q75], and Q4 > q75. Quantiles use linear interpolation; ties stay together in the lower interval at each boundary. PWP thresholds remain fixed in Data S9, whereas coefficient thresholds are run-specific. Exact thresholds are retained in the threshold CSV files.

`n`, `joint_n_*`, `joint_beta_Q1_n` and `beta_most_negative_quartile_n` count grids in the indicated set. `PWP_quartile_n`, `PWP_tail_n` and `denominator` count the complete corresponding within-morphology PWP interval, not the coefficient quartile. `row_percent`, `percent_of_PWP_quartile` and `percent_1400`/`percent_1600` use that complete PWP interval as denominator. For sector-specific tails, `*_PWP_tail_sector_N` is the complete PWP tail within the same morphology and sector, and `*_percent_of_PWP_tail_in_sector` is 100 × joint n/N.

`percent_of_selected_extreme` describes a sector's share of the selected joint tail set. This differs from `percent_of_PWP_quartile_in_sector`, which uses all cells in that morphology's PWP tail within the sector. In Table S8e, `original_*_fit_percent_of_joint` uses the row's joint set as denominator. The three corresponding `original_*_fit_n` counts sum to `joint_beta_Q1_n`.

## Distribution and comparison fields

Suffixes `min`, `q05`, `q25`, `q50`, `median`, `q75`, `q95`, `max`, `mean` and `sd` denote the named distribution summaries of the field prefix. `height_*` refers to mean building height; `G1_*` to the green-quantity score; `PWP_*` to °C; coefficient prefixes to standardised-model coefficients. `n_valid` counts finite observations for the variable. `small_group_n_lt_30` flags groups with fewer than 30 grids. An empty group's distribution summaries are missing, not zero; its count is retained as zero.

`spearman_rho` is the existing descriptive Spearman rank correlation for the stated pair and grouping level. `n_unique_*` counts distinct values; `n_redundant_tied_*` counts observations beyond those distinct values; `n_excluded_nonfinite` counts excluded nonfinite pairs. `status` records whether the correlation is defined. No p values are supplied in these rank-description files.

`coefficient_low`, `coefficient_mid` and `coefficient_high` are signed medians in the three existing local-fit classes; `observed_*` fields refer to the corresponding unranked indicator medians. Full-order fields sort medians from low to high and retain exact ties. Minimum/maximum-class fields retain all classes tied at an endpoint. A shared complete order requires all three positions to agree across all four morphologies; a shared endpoint alone is not a shared complete order.

In Data S9, `delta_1600_minus_1400_pp` is the change in overlap in percentage points, while `hot_minus_cool_*_pp` subtracts the cool-tail overlap from the hot-tail overlap for one run. `direction_preserved` records agreement of that direction between runs. `Q1_membership_changed` flags entry to or exit from the lowest coefficient quartile. `retained_Q1_n`, `entered_Q1_1600_n`, `exited_Q1_1400_n` and `membership_changed_n` describe memberships and changes; the cool/hot entry and exit fields further locate those changes within the fixed PWP tails.

Counts are grid counts, not independent replicates. Distribution intervals are not confidence intervals. These data preserve the within-model, spatially dependent comparisons reported in the manuscript.
