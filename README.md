# Data accompanying the study

Surface thermal differences and grey–green space–temperature associations across urban morphologies in Beijing

Repository: https://github.com/weiren2024/beijing-morphology-local-thermal-associations

## Contents

The `data` directory contains the 22 numerical CSV files supplied as Supplementary Data S6, S8 and S9. These study-derived grid records, model outputs and summary tables support the manuscript's morphology, local-fit and same-grid thermal–coefficient comparisons.

| Directory | Numerical CSV files | Record content |
| --- | ---: | --- |
| `data/Data_S6` | 2 | Two 96-row morphology × local-fit class × indicator summaries underlying Figures 9–10. |
| `data/Data_S8` | 14 | All 4,005 joined grid records, complete quartile counts and thresholds, same-grid condition summaries, eight-indicator comparisons and sector descriptions underlying Figures 11–12 and Table S8. |
| `data/Data_S9` | 6 | Existing-output comparison at neighbourhood-search lower bounds of 1,400 and 1,600, with complete thresholds and membership identities supporting Table S9. |

Each directory contains a scientific data guide, a field inventory, the shared data dictionary and complete indicator definitions. `Supplementary_Material_EN.md` gives the published-table context, including exact local-fit boundaries and the model settings. `file_manifest_sha256.csv` identifies the numerical files by checksum.

## Interpreting and joining the data

`LID` is the stable analysis-grid identifier; `RUN_ROWID` preserves the model-run row identity. Grid-centroid coordinates are in EPSG:32650 and metres. The dependent measure is total-population-weighted summer daytime land-surface temperature (PWP, °C). Model coefficients are signed coefficients after Y and X standardisation to mean zero and standard deviation one. `CanopyHeight_Mean` in `joint_grid.csv` is in cm; supplementary display tables express canopy height in m.

The four morphology codes are 1 = Compact, 2 = Open mid-/high-rise, 3 = Open low-rise and 4 = Green-space type. The three local-fit codes are 1 = lower, 2 = intermediate and 3 = higher. Quartiles are defined separately within morphology, with boundary ties assigned to the lower interval. The data dictionary specifies the complete denominators, missing values, fixed sectors and field families.

The counts describe spatially dependent study grids. Distribution intervals report observed variation, and model coefficients describe associations in the fitted model. Main-text comparisons use the 1,600-neighbourhood-lower-bound output; Data S9 also retains the existing 1,400 output for the specified comparison.

## Source products

`Source_products_EN.md` identifies the five third-party source products and their access pages, as cited in manuscript Table 1. The repository contains study-derived grid data and result summaries; the original third-party raster products and building polygons are obtained from their providers.
