# Supplementary material

Surface thermal differences and grey–green space–temperature associations across urban morphologies in Beijing

# Supplementary tables

**Supplementary Table S1a. Candidate indicators and complete component formulas.**

| Measurement dimension | Candidate indicator or field | Number of indicators | Definition or calculation | Unit |
| --- | --- | --- | --- | --- |
| Built-space vertical structure | `BuildHeight_Mean` | 1 | Arithmetic mean of valid heights within building-covered areas | m |
| Vegetation vertical structure | `CanopyHeight_Mean` | 1 | Arithmetic mean of valid height pixels within the grid, including valid zeros | m |
| Green-quantity score (G1) | `G1_score` | 1 | $z(G\_CA)$ | 0–1 score |
| Green fragmentation–extension score (G2) | `G2_score` | 1 | $0.0885z(G\_SPLIT)+0.4881[1-z(G\_MESH)]+0.4234[1-z(G\_GYRATE\_MN)]$ | 0–1 score |
| Green connectivity–interspersion score (G3) | `G3_score` | 1 | $0.2151z(G\_CONTIG\_MN)+0.5377z(G\_IJI)+0.2472[1-z(G\_LSI)]$ | 0–1 score |
| Grey-quantity score (B1) | `B1_score` | 1 | $z(B\_PLAND)$ | 0–1 score |
| Grey fragmentation–boundary score (B2) | `B2_score` | 1 | $0.0272z(B\_SPLIT)+0.6578[1-z(B\_MESH)]+0.3150[1-z(B\_TE)]$ | 0–1 score |
| Grey connectivity–interspersion score (B3) | `B3_score` | 1 | $0.2313z(B\_CONTIG\_MN)+0.5124z(B\_IJI)+0.2563[1-z(B\_LSI)]$ | 0–1 score |
| Green topological structure | `GCORE_Pct`, `GISLET_Pct`, `GPERF_Pct`, `GEDGE_Pct`, `GLOOP_Pct`, `GBRDG_Pct`, `GBRNCH_Pct` | 7 | Area of each MSPA structure as a percentage of total green MSPA foreground area | % |
| Grey topological structure | `BCORE_Pct`, `BISLET_Pct`, `BPERF_Pct`, `BEDGE_Pct`, `BLOOP_Pct`, `BBRDG_Pct`, `BBRNCH_Pct` | 7 | Area of each MSPA structure as a percentage of total grey MSPA foreground area | % |

Note. CA, class area; PLAND, percentage of landscape; SPLIT, splitting index; MESH, effective mesh size; GYRATE_MN, mean radius of gyration; CONTIG_MN, mean contiguity index; IJI, interspersion and juxtaposition index; LSI, landscape shape index; TE, total edge length. z denotes min–max scaling. MSPA percentages use the summed area of seven structures in the corresponding foreground, including valid external and internal foreground codes; background and missing codes are excluded.

**Supplementary Table S1b. Indicator-selection records.**

| Field | Measurement dimension | Selection | Selection rationale | Statistic |
| --- | --- | --- | --- | --- |
| CanopyHeight_Mean | Vegetation vertical structure | Retained | Retain vegetation vertical structure | VIF=1.0157 |
| BuildHeight_Mean | Built-space vertical structure | Retained | Retain building vertical structure | VIF=2.0457 |
| G1_score | Green quantity | Retained | Use G1 to represent quantity and reduce redundancy with B1 and B2 | VIF=4.4503 |
| G2_score | Green fragmentation–extension configuration | Retained | Retain planar configuration information | VIF=2.1821 |
| G3_score | Green connectivity–interspersion configuration | Retained | Retain a complementary planar configuration dimension | VIF=2.8399 |
| B1_score | Grey quantity | Excluded | Highly correlated with G1; quantity represented by G1 | r_with_G1=-0.9912 |
| B2_score | Grey fragmentation–boundary configuration | Excluded | Highly correlated with G1; retain G1 as the quantity indicator | r_with_G1=0.9003 |
| B3_score | Grey connectivity–interspersion configuration | Retained | Retain grey configuration information | VIF=2.0228 |
| GCORE_Pct | Green Core structure | Excluded | Highly correlated with G1; avoid redundant quantity information | r_with_G1=0.8548 |
| GISLET_Pct | Green Islet structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |
| GPERF_Pct | Green Perforation structure | Excluded | Use Bridge as the topological indicator | zero_pct=88.6392; Compact_zero=646/646 |
| GEDGE_Pct | Green Edge structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |
| GLOOP_Pct | Green Loop structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |
| GBRDG_Pct | Green Bridge structure | Retained | Add inter-core connecting information for green space | VIF=1.1592; max_abs_r_with_base6=0.2694 |
| GBRNCH_Pct | Green Branch structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |
| BCORE_Pct | Grey Core structure | Excluded | Highly correlated with G1; avoid redundant quantity information | r_with_G1=-0.8833 |
| BISLET_Pct | Grey Islet structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |
| BPERF_Pct | Grey Perforation structure | Excluded | Use Bridge as the topological indicator | zero_pct=85.3184; Green_space_nonzero=2/1640 |
| BEDGE_Pct | Grey Edge structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |
| BLOOP_Pct | Grey Loop structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |
| BBRDG_Pct | Grey Bridge structure | Retained | Add inter-core connecting information for grey space | VIF=1.1865; max_abs_r_with_base6=0.3028 |
| BBRNCH_Pct | Grey Branch structure | Excluded | Use Bridge as the topological indicator | Valid and nonconstant |

Note. Representative indicators were selected to retain quantity, configuration, vertical structure, and connecting structure. Absolute unrounded Pearson correlations >0.70 flagged redundancy; VIF <5 was used to check the retained combination.

### S1c. Score aggregation and height summaries

Single-component scores use the corresponding scaled value. Multi-component scores sum the available components using fixed weights; weights are not renormalised when a component is missing. A score is zero when all components are missing, and units without the corresponding foreground retain zero. IJI is undefined when fewer than three landscape classes are present (FRAGSTATS, n.d.); missing IJI components follow the same aggregation rule. Complete component formulas are given in Table S1a. Building height is summarised over building-covered areas. Canopy height is summarised over valid height pixels within each unit, including valid zeros. Definitions are provided in Sections 2.3.2–2.3.3 of the main text.

**Supplementary Table S2a. Pearson correlation matrix of the retained explanatory variables.**

| Field | CanopyHeight_Mean | BuildHeight_Mean | GBRDG_Pct | BBRDG_Pct | G1_score | G2_score | G3_score | B3_score |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| CanopyHeight_Mean | 1.0000 | 0.0343 | -0.0211 | 0.0521 | -0.0108 | 0.0720 | 0.0622 | 0.0218 |
| BuildHeight_Mean | 0.0343 | 1.0000 | -0.2694 | -0.1827 | -0.6414 | -0.0773 | -0.3853 | 0.3153 |
| GBRDG_Pct | -0.0211 | -0.2694 | 1.0000 | 0.1478 | 0.2228 | 0.1499 | 0.2194 | -0.1747 |
| BBRDG_Pct | 0.0521 | -0.1827 | 0.1478 | 1.0000 | 0.0606 | 0.3028 | 0.0649 | -0.0426 |
| G1_score | -0.0108 | -0.6414 | 0.2228 | 0.0606 | 1.0000 | -0.3165 | 0.4584 | -0.4630 |
| G2_score | 0.0720 | -0.0773 | 0.1499 | 0.3028 | -0.3165 | 1.0000 | 0.3153 | 0.2813 |
| G3_score | 0.0622 | -0.3853 | 0.2194 | 0.0649 | 0.4584 | 0.3153 | 1.0000 | 0.2332 |
| B3_score | 0.0218 | 0.3153 | -0.1747 | -0.0426 | -0.4630 | 0.2813 | 0.2332 | 1.0000 |

Note. n = 4,005. Linear conversion of canopy-height units does not change the correlation coefficients.

**Supplementary Table S2b. Variance inflation factors of the retained explanatory variables.**

| Field | VIF |
| --- | --- |
| CanopyHeight_Mean | 1.0157 |
| BuildHeight_Mean | 2.0457 |
| GBRDG_Pct | 1.1592 |
| BBRDG_Pct | 1.1865 |
| G1_score | 4.4503 |
| G2_score | 2.1821 |
| G3_score | 2.8399 |
| B3_score | 2.0228 |

Note. VIFs were calculated for the same retained variable combination; the maximum is 4.4503.

**Supplementary Table S2c. Descriptive statistics of the dependent variable and retained explanatory variables.**

| Indicator | Unit | n | Mean | SD | Q25 | Median | Q75 | Minimum | Maximum |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Total-population-weighted daytime land-surface temperature | °C | 4005 | 32.5205 | 1.5244 | 31.4426 | 32.2256 | 33.5208 | 27.5533 | 36.8879 |
| Mean building height | m | 4005 | 11.8469 | 4.8016 | 8.3054 | 9.7662 | 14.2937 | 6.0553 | 35.0215 |
| Grid-mean canopy height | m | 4005 | 0.4525 | 1.5723 | 0.0000 | 0.0000 | 0.0000 | 0.0000 | 16.3394 |
| Green-quantity score (G1) | 0–1 score | 4005 | 0.4432 | 0.3308 | 0.0923 | 0.4646 | 0.7428 | 0.0000 | 1.0000 |
| Green fragmentation–extension score (G2) | 0–1 score | 4005 | 0.5013 | 0.3039 | 0.2282 | 0.5520 | 0.7909 | 0.0000 | 1.0000 |
| Green connectivity–interspersion score (G3) | 0–1 score | 4005 | 0.3825 | 0.2083 | 0.3056 | 0.3760 | 0.4402 | 0.0000 | 0.9860 |
| Grey connectivity–interspersion score (B3) | 0–1 score | 4005 | 0.4355 | 0.1520 | 0.3371 | 0.4120 | 0.4801 | 0.0000 | 0.9908 |
| Green Bridge proportion | % | 4005 | 18.0066 | 25.2035 | 0.0000 | 0.0627 | 32.5860 | 0.0000 | 100.0000 |
| Grey Bridge proportion | % | 4005 | 13.4116 | 22.3330 | 0.0000 | 0.0000 | 20.4843 | 0.0000 | 97.8774 |

Note. n = 4,005. SD uses n − 1 in the denominator. Canopy height is reported in m after conversion from the model-input unit of cm; this reporting conversion does not change the fitted input, relative ranks, or scaled-model coefficients.

**Supplementary Table S3a. GWR/MGWR specifications and diagnostics.**

| Item | Value or setting | Description |
| --- | --- | --- |
| Number of analysis units | 4005 | All included analysis units |
| Dependent variable | PWP_Day_total | Total-population-weighted daytime land-surface temperature; common valid pixels |
| Explanatory variables | CanopyHeight_Mean; BuildHeight_Mean; GBRDG_Pct; BBRDG_Pct; G1_score; G2_score; G3_score; B3_score | One study-wide model fitted to all 4,005 units |
| Software | ArcGIS Pro 3.7 | Continuous-outcome MGWR |
| Neighbourhood and kernel | Adaptive NUMBER_OF_NEIGHBORS; BISQUARE | Adaptive neighbour count; bi-square kernel |
| Neighbourhood selection | GOLDEN_SEARCH | Search range: 1,600–4,005 neighbours |
| Data scaling | SCALE_DATA | Variables standardised to mean zero and standard deviation one; standardised coefficients used for comparisons |
| GWR R² | 0.7302 | Software diagnostic output |
| MGWR R² | 0.7439 | Software diagnostic output |
| GWR adjusted R² | 0.7255 | Software diagnostic output |
| MGWR adjusted R² | 0.7407 | Software diagnostic output |
| GWR AICc | 6224.3530 | Software diagnostic output |
| MGWR AICc | 6012.8254 | Software diagnostic output |
| GWR σ² | 0.2745 | Software diagnostic output |
| MGWR σ² | 0.2593 | Software diagnostic output |
| GWR Sigma-Squared MLE | 0.2698 | Software diagnostic output |
| MGWR Sigma-Squared MLE | 0.2561 | Software diagnostic output |
| GWR effective degrees of freedom | 3936.5792 | Software diagnostic output |
| MGWR effective degrees of freedom | 3955.4514 | Software diagnostic output |
| GWR−MGWR AICc | 211.5276 | Comparison under the same fitting specification |
| RMSE in original units | 0.7714 | °C; in-sample residual summary |
| Maximum local condition number | 15.3919 | CND_NUMBER |
| Number of units with a local condition number >30 | 0 | Local condition-number threshold: 30 |
| Minimum Local R² | 0.4942 | Continuous local fit |
| Local R² Q25 | 0.5489 | Continuous local fit |
| Median Local R² | 0.6411 | Continuous local fit |
| Local R² Q75 | 0.7075 | Continuous local fit |
| Maximum Local R² | 0.7732 | Continuous local fit |
| Residual Moran's I | 0.5444 | Scaled MGWR residuals |
| Residual permutation p | 0.001 | Two-sided permutation diagnostic around the expected I |
| Residual spatial weights | directed KNN, row standardised; distance ties by sorted RUN_ROWID | KNN k=8 |
| Number of permutations | 999 | Residual spatial-autocorrelation diagnostic |
| Permutation seed | 20261001 | Random seed |

Note. R², AICc, and local condition numbers are taken from model output. Residual Moran’s I uses the spatial weights and permutation settings listed above.

**Supplementary Table S3b. Bandwidths and scaled-model local-coefficient summaries.**

| Indicator | Neighbours | Neighbour share (%) | Coefficient median | Units flagged significant after software correction | Software-corrected significant share (%) |
| --- | --- | --- | --- | --- | --- |
| Intercept | 1600 | 39.95 | 0.0783 | 3320 | 82.90 |
| CanopyHeight_Mean | 1600 | 39.95 | 0.0147 | 2753 | 68.74 |
| BuildHeight_Mean | 1600 | 39.95 | 0.0499 | 1759 | 43.92 |
| GBRDG_Pct | 1600 | 39.95 | -0.0350 | 1843 | 46.02 |
| BBRDG_Pct | 1600 | 39.95 | -0.0183 | 521 | 13.01 |
| G1_score | 1600 | 39.95 | -0.5922 | 4005 | 100.00 |
| G2_score | 1600 | 39.95 | -0.1591 | 4005 | 100.00 |
| G3_score | 1600 | 39.95 | -0.0040 | 45 | 1.12 |
| B3_score | 1600 | 39.95 | -0.0533 | 1573 | 39.28 |

Note. The intercept and eight explanatory variables are included. All selected neighbourhoods contain 1,600 neighbours, at the lower bound of the specified search range. Significant shares are the percentages of units carrying the software-corrected significance flag.

**Supplementary Table S3c. Diagnostics of the two existing MGWR runs with different neighbourhood-search lower bounds.**

| Diagnostic or setting | Lower bound 1,400 | Lower bound 1,600 |
| --- | ---: | ---: |
| Analysis units | 4005 | 4005 |
| Neighbourhood search range | 1,400–4,005 | 1,600–4,005 |
| Selected neighbours for all coefficients, including the intercept | 1400 | 1600 |
| MGWR R² | 0.7558 | 0.7439 |
| MGWR adjusted R² | 0.7522 | 0.7407 |
| MGWR AICc | 5838.1863 | 6012.8254 |
| Maximum local condition number | 38.0984 | 15.3919 |
| Units with a local condition number >30 | 8 | 0 |
| Units with a local condition number >30 (%) | 0.20 | 0.00 |
| Residual Moran's I | 0.5367 | 0.5444 |

Note. Both runs use the same 4,005 grid cells, response, eight explanatory variables, adaptive bi-square kernel and software standardisation (mean zero and standard deviation one). The lower-bound increase reduced the local condition-number warnings but also reduced R² and increased AICc; the 1,600 output is used for the main-text fit zones and coefficient summaries. The residual diagnostics use the identical settings in Table S3a. The cool/hot-tail overlap comparison in Table S9 uses these existing coefficient outputs without refitting either model.

**Supplementary Table S4. Exact boundaries, intervals, and counts of the three Local R² classes.**

| Class | Local-fit class | Interval | Units | Share of all units (%) |
| --- | --- | --- | --- | --- |
| 1 | Lower fit | $R^2_{local}\leq b_1$ | 1553 | 38.78 |
| 2 | Intermediate fit | $b_1<R^2_{local}\leq b_2$ | 1207 | 30.14 |
| 3 | Higher fit | $R^2_{local}>b_2$ | 1245 | 31.09 |

Note. n = 4,005. Fisher–Jenks natural breaks define lower, intermediate, and higher local fit. Exact boundaries are b₁ = 0.5996587937977012 and b₂ = 0.6938686896878181. The rounded values 0.60 and 0.69 are used in the main text and figures; unit assignments use the exact boundaries. Percentages are rounded to two decimal places.

**Supplementary Table S5. Cross-tabulation of four urban morphologies and three local-fit classes.**

| Urban morphology | Lower fit | Intermediate fit | Higher fit | Total |
| --- | --- | --- | --- | --- |
| Compact | 54 (8.36%) | 201 (31.11%) | 391 (60.53%) | 646 |
| Open mid-/high-rise | 265 (25.02%) | 306 (28.90%) | 488 (46.08%) | 1059 |
| Open low-rise | 279 (42.27%) | 212 (32.12%) | 169 (25.61%) | 660 |
| Green-space type | 955 (58.23%) | 488 (29.76%) | 197 (12.01%) | 1640 |

Note. Values in parentheses are percentages within each morphology. The four morphologies contain 4,005 units in total; the smallest cross-classified group contains 54 units.

**Supplementary Table S6a. Within-morphology relative indicator levels and model-input values by cross-classified group.**

| Morphology | Fit class | Indicator | n | Relative level Q25 | Relative level median | Relative level Q75 | Model-input median | Model-input unit |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Compact | 1 | Mean building height | 54 | -0.7794 | -0.5743 | -0.1153 | 11.8646 | m |
| Compact | 1 | Grid-mean canopy height | 54 | -0.2353 | -0.2353 | -0.2353 | 0.0000 | m |
| Compact | 1 | Green-quantity score (G1) | 54 | -0.3115 | 0.5735 | 0.7601 | 0.0687 | 0–1 score |
| Compact | 1 | Green fragmentation–extension score (G2) | 54 | 0.1169 | 0.3576 | 0.5364 | 0.8161 | 0–1 score |
| Compact | 1 | Green connectivity–interspersion score (G3) | 54 | 0.1134 | 0.2786 | 0.5534 | 0.3088 | 0–1 score |
| Compact | 1 | Grey connectivity–interspersion score (B3) | 54 | -0.7825 | -0.5372 | 0.1192 | 0.4634 | 0–1 score |
| Compact | 1 | Green Bridge proportion | 54 | -0.1115 | -0.1115 | 0.8150 | 0.0000 | % |
| Compact | 1 | Grey Bridge proportion | 54 | -0.1656 | -0.1656 | 0.7864 | 0.0000 | % |
| Compact | 2 | Mean building height | 201 | -0.6378 | -0.1424 | 0.5635 | 15.4917 | m |
| Compact | 2 | Grid-mean canopy height | 201 | -0.2353 | -0.2353 | 0.5944 | 0.0000 | m |
| Compact | 2 | Green-quantity score (G1) | 201 | -0.4520 | -0.4520 | 0.6409 | 0.0000 | 0–1 score |
| Compact | 2 | Green fragmentation–extension score (G2) | 201 | -0.4551 | -0.4551 | 0.4861 | 0.0000 | 0–1 score |
| Compact | 2 | Green connectivity–interspersion score (G3) | 201 | -0.4551 | -0.4551 | 0.4737 | 0.0000 | 0–1 score |
| Compact | 2 | Grey connectivity–interspersion score (B3) | 201 | -0.6316 | 0.1192 | 0.5882 | 0.4801 | 0–1 score |
| Compact | 2 | Green Bridge proportion | 201 | -0.1115 | -0.1115 | -0.1115 | 0.0000 | % |
| Compact | 2 | Grey Bridge proportion | 201 | -0.1656 | -0.1656 | -0.1656 | 0.0000 | % |
| Compact | 3 | Mean building height | 391 | -0.3050 | 0.1362 | 0.5186 | 17.3419 | m |
| Compact | 3 | Grid-mean canopy height | 391 | -0.2353 | -0.2353 | -0.2353 | 0.0000 | m |
| Compact | 3 | Green-quantity score (G1) | 391 | -0.4520 | -0.4520 | 0.3351 | 0.0000 | 0–1 score |
| Compact | 3 | Green fragmentation–extension score (G2) | 391 | -0.4551 | -0.4551 | 0.4752 | 0.0000 | 0–1 score |
| Compact | 3 | Green connectivity–interspersion score (G3) | 391 | -0.4551 | -0.4551 | 0.5031 | 0.0000 | 0–1 score |
| Compact | 3 | Grey connectivity–interspersion score (B3) | 391 | -0.3707 | 0.1192 | 0.5882 | 0.4801 | 0–1 score |
| Compact | 3 | Green Bridge proportion | 391 | -0.1115 | -0.1115 | -0.1115 | 0.0000 | % |
| Compact | 3 | Grey Bridge proportion | 391 | -0.1656 | -0.1656 | -0.1656 | 0.0000 | % |
| Open mid-/high-rise | 1 | Mean building height | 265 | -0.6827 | -0.2219 | 0.1671 | 13.8568 | m |
| Open mid-/high-rise | 1 | Grid-mean canopy height | 265 | -0.2691 | -0.2691 | -0.2691 | 0.0000 | m |
| Open mid-/high-rise | 1 | Green-quantity score (G1) | 265 | 0.0255 | 0.4561 | 0.7602 | 0.4495 | 0–1 score |
| Open mid-/high-rise | 1 | Green fragmentation–extension score (G2) | 265 | -0.5033 | -0.2465 | 0.2408 | 0.6566 | 0–1 score |
| Open mid-/high-rise | 1 | Green connectivity–interspersion score (G3) | 265 | -0.2710 | 0.1445 | 0.5524 | 0.3854 | 0–1 score |
| Open mid-/high-rise | 1 | Grey connectivity–interspersion score (B3) | 265 | -0.6657 | -0.2899 | 0.4429 | 0.4171 | 0–1 score |
| Open mid-/high-rise | 1 | Green Bridge proportion | 265 | -0.3720 | 0.3163 | 0.6223 | 3.2134 | % |
| Open mid-/high-rise | 1 | Grey Bridge proportion | 265 | -0.4523 | -0.4523 | 0.5184 | 0.0000 | % |
| Open mid-/high-rise | 2 | Mean building height | 306 | -0.5331 | -0.0755 | 0.5283 | 14.4299 | m |
| Open mid-/high-rise | 2 | Grid-mean canopy height | 306 | -0.2691 | -0.2691 | -0.2691 | 0.0000 | m |
| Open mid-/high-rise | 2 | Green-quantity score (G1) | 306 | -0.4023 | 0.0293 | 0.4915 | 0.1763 | 0–1 score |
| Open mid-/high-rise | 2 | Green fragmentation–extension score (G2) | 306 | -0.4773 | 0.0387 | 0.5009 | 0.7727 | 0–1 score |
| Open mid-/high-rise | 2 | Green connectivity–interspersion score (G3) | 306 | -0.4854 | 0.0066 | 0.4991 | 0.3670 | 0–1 score |
| Open mid-/high-rise | 2 | Grey connectivity–interspersion score (B3) | 306 | -0.4854 | -0.0255 | 0.5274 | 0.4584 | 0–1 score |
| Open mid-/high-rise | 2 | Green Bridge proportion | 306 | -0.3720 | -0.3720 | 0.5798 | 0.0000 | % |
| Open mid-/high-rise | 2 | Grey Bridge proportion | 306 | -0.4523 | -0.1756 | 0.5420 | 0.0422 | % |
| Open mid-/high-rise | 3 | Mean building height | 488 | -0.3555 | 0.2049 | 0.5963 | 15.9493 | m |
| Open mid-/high-rise | 3 | Grid-mean canopy height | 488 | -0.2691 | -0.2691 | 0.7195 | 0.0000 | m |
| Open mid-/high-rise | 3 | Green-quantity score (G1) | 488 | -0.6577 | -0.2748 | 0.2262 | 0.0753 | 0–1 score |
| Open mid-/high-rise | 3 | Green fragmentation–extension score (G2) | 488 | -0.5009 | 0.1492 | 0.5822 | 0.8032 | 0–1 score |
| Open mid-/high-rise | 3 | Green connectivity–interspersion score (G3) | 488 | -0.6398 | -0.0935 | 0.4396 | 0.3573 | 0–1 score |
| Open mid-/high-rise | 3 | Grey connectivity–interspersion score (B3) | 488 | -0.3319 | 0.1464 | 0.5175 | 0.4753 | 0–1 score |
| Open mid-/high-rise | 3 | Green Bridge proportion | 488 | -0.3720 | -0.3720 | 0.2696 | 0.0000 | % |
| Open mid-/high-rise | 3 | Grey Bridge proportion | 488 | -0.4523 | -0.4523 | 0.4358 | 0.0000 | % |
| Open low-rise | 1 | Mean building height | 279 | -0.5833 | -0.1061 | 0.3727 | 8.8247 | m |
| Open low-rise | 1 | Grid-mean canopy height | 279 | -0.1333 | -0.1333 | -0.1333 | 0.0000 | m |
| Open low-rise | 1 | Green-quantity score (G1) | 279 | -0.3818 | 0.1545 | 0.5432 | 0.3716 | 0–1 score |
| Open low-rise | 1 | Green fragmentation–extension score (G2) | 279 | -0.5909 | -0.1515 | 0.3773 | 0.7574 | 0–1 score |
| Open low-rise | 1 | Green connectivity–interspersion score (G3) | 279 | -0.4061 | 0.0424 | 0.5318 | 0.3504 | 0–1 score |
| Open low-rise | 1 | Grey connectivity–interspersion score (B3) | 279 | -0.4591 | 0.0152 | 0.4985 | 0.4229 | 0–1 score |
| Open low-rise | 1 | Green Bridge proportion | 279 | -0.6212 | 0.0576 | 0.4682 | 16.4259 | % |
| Open low-rise | 1 | Grey Bridge proportion | 279 | -0.5045 | -0.0545 | 0.4424 | 16.7224 | % |
| Open low-rise | 2 | Mean building height | 212 | -0.4652 | 0.0515 | 0.5652 | 9.0454 | m |
| Open low-rise | 2 | Grid-mean canopy height | 212 | -0.1333 | -0.1333 | -0.1333 | 0.0000 | m |
| Open low-rise | 2 | Green-quantity score (G1) | 212 | -0.4492 | 0.0333 | 0.5992 | 0.3485 | 0–1 score |
| Open low-rise | 2 | Green fragmentation–extension score (G2) | 212 | -0.4523 | -0.0136 | 0.5167 | 0.7734 | 0–1 score |
| Open low-rise | 2 | Green connectivity–interspersion score (G3) | 212 | -0.5530 | -0.0530 | 0.4568 | 0.3386 | 0–1 score |
| Open low-rise | 2 | Grey connectivity–interspersion score (B3) | 212 | -0.5439 | -0.0621 | 0.4023 | 0.4110 | 0–1 score |
| Open low-rise | 2 | Green Bridge proportion | 212 | -0.6212 | 0.0652 | 0.5371 | 16.5767 | % |
| Open low-rise | 2 | Grey Bridge proportion | 212 | -0.4742 | 0.0288 | 0.4659 | 20.3943 | % |
| Open low-rise | 3 | Mean building height | 169 | -0.3455 | 0.2091 | 0.5879 | 9.3045 | m |
| Open low-rise | 3 | Grid-mean canopy height | 169 | -0.1333 | -0.1333 | 0.8242 | 0.0000 | m |
| Open low-rise | 3 | Green-quantity score (G1) | 169 | -0.7333 | -0.2758 | 0.2091 | 0.2724 | 0–1 score |
| Open low-rise | 3 | Green fragmentation–extension score (G2) | 169 | -0.2333 | 0.2212 | 0.6879 | 0.8022 | 0–1 score |
| Open low-rise | 3 | Green connectivity–interspersion score (G3) | 169 | -0.6121 | -0.0212 | 0.5000 | 0.3415 | 0–1 score |
| Open low-rise | 3 | Grey connectivity–interspersion score (B3) | 169 | -0.4758 | 0.0485 | 0.5545 | 0.4260 | 0–1 score |
| Open low-rise | 3 | Green Bridge proportion | 169 | -0.6212 | -0.1273 | 0.4455 | 4.9966 | % |
| Open low-rise | 3 | Grey Bridge proportion | 169 | -0.4879 | 0.1000 | 0.5848 | 23.3465 | % |
| Green-space type | 1 | Mean building height | 955 | -0.5701 | -0.1000 | 0.4439 | 8.1776 | m |
| Green-space type | 1 | Grid-mean canopy height | 955 | -0.0811 | -0.0811 | -0.0811 | 0.0000 | m |
| Green-space type | 1 | Green-quantity score (G1) | 955 | -0.4701 | 0.0457 | 0.5348 | 0.7724 | 0–1 score |
| Green-space type | 1 | Green fragmentation–extension score (G2) | 955 | -0.5421 | -0.0549 | 0.4445 | 0.3524 | 0–1 score |
| Green-space type | 1 | Green connectivity–interspersion score (G3) | 955 | -0.4476 | 0.0220 | 0.4994 | 0.4165 | 0–1 score |
| Green-space type | 1 | Grey connectivity–interspersion score (B3) | 955 | -0.4299 | 0.0598 | 0.5238 | 0.3568 | 0–1 score |
| Green-space type | 1 | Green Bridge proportion | 955 | -0.6921 | -0.0573 | 0.4457 | 11.9491 | % |
| Green-space type | 1 | Grey Bridge proportion | 955 | -0.3659 | -0.3659 | 0.4396 | 0.0000 | % |
| Green-space type | 2 | Mean building height | 488 | -0.3409 | 0.1220 | 0.5070 | 8.4456 | m |
| Green-space type | 2 | Grid-mean canopy height | 488 | -0.0811 | -0.0811 | -0.0811 | 0.0000 | m |
| Green-space type | 2 | Green-quantity score (G1) | 488 | -0.5027 | -0.0338 | 0.4482 | 0.7557 | 0–1 score |
| Green-space type | 2 | Green fragmentation–extension score (G2) | 488 | -0.4213 | 0.0701 | 0.5503 | 0.3947 | 0–1 score |
| Green-space type | 2 | Green connectivity–interspersion score (G3) | 488 | -0.5488 | -0.0299 | 0.4776 | 0.4130 | 0–1 score |
| Green-space type | 2 | Grey connectivity–interspersion score (B3) | 488 | -0.5543 | -0.0665 | 0.4707 | 0.3447 | 0–1 score |
| Green-space type | 2 | Green Bridge proportion | 488 | -0.6921 | 0.0860 | 0.5582 | 19.0977 | % |
| Green-space type | 2 | Grey Bridge proportion | 488 | -0.3659 | -0.3659 | 0.5034 | 0.0000 | % |
| Green-space type | 3 | Mean building height | 197 | -0.5854 | 0.0902 | 0.7085 | 8.3995 | m |
| Green-space type | 3 | Grid-mean canopy height | 197 | -0.0811 | -0.0811 | 0.9293 | 0.0000 | m |
| Green-space type | 3 | Green-quantity score (G1) | 197 | -0.5878 | -0.1280 | 0.3951 | 0.7322 | 0–1 score |
| Green-space type | 3 | Green fragmentation–extension score (G2) | 197 | -0.4195 | 0.1817 | 0.6012 | 0.4271 | 0–1 score |
| Green-space type | 3 | Green connectivity–interspersion score (G3) | 197 | -0.5634 | -0.0293 | 0.5226 | 0.4132 | 0–1 score |
| Green-space type | 3 | Grey connectivity–interspersion score (B3) | 197 | -0.6549 | -0.1841 | 0.3817 | 0.3324 | 0–1 score |
| Green-space type | 3 | Green Bridge proportion | 197 | -0.6921 | 0.0768 | 0.5963 | 18.5474 | % |
| Green-space type | 3 | Grey Bridge proportion | 197 | -0.3659 | 0.2902 | 0.6573 | 0.4367 | % |

Note. There are 96 records: four morphologies × three local-fit classes × eight indicators. Relative levels use all units in each morphology as the reference, with average-rank percentile q transformed as d = 2(q − 0.5); ties receive average ranks. Model-input canopy height is reported in m. Complete quantiles, means, and SDs are provided in `TableS6a_indicator_rank_and_raw_profiles.csv`.

**Supplementary Table S6b. Scaled-model local coefficients by morphology and local-fit class.**

| Morphology | Fit class | Indicator | n | Coefficient Q25 | Coefficient median | Coefficient Q75 | Software-corrected significant share (%) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Compact | 1 | Mean building height | 54 | 0.0478 | 0.1042 | 0.1442 | 70.37 |
| Compact | 1 | Grid-mean canopy height | 54 | -0.0347 | -0.0245 | 0.0143 | 29.63 |
| Compact | 1 | Green-quantity score (G1) | 54 | -0.5590 | -0.5412 | -0.5217 | 100.00 |
| Compact | 1 | Green fragmentation–extension score (G2) | 54 | -0.1448 | -0.1355 | -0.1219 | 100.00 |
| Compact | 1 | Green connectivity–interspersion score (G3) | 54 | -0.0205 | -0.0144 | -0.0057 | 0.00 |
| Compact | 1 | Grey connectivity–interspersion score (B3) | 54 | -0.0713 | -0.0660 | -0.0555 | 74.07 |
| Compact | 1 | Green Bridge proportion | 54 | -0.0723 | -0.0655 | -0.0613 | 81.48 |
| Compact | 1 | Grey Bridge proportion | 54 | -0.0270 | -0.0131 | -0.0058 | 12.96 |
| Compact | 2 | Mean building height | 201 | -0.0015 | 0.0130 | 0.0278 | 1.49 |
| Compact | 2 | Grid-mean canopy height | 201 | 0.0029 | 0.0511 | 0.0779 | 55.22 |
| Compact | 2 | Green-quantity score (G1) | 201 | -0.7706 | -0.7280 | -0.6544 | 100.00 |
| Compact | 2 | Green fragmentation–extension score (G2) | 201 | -0.1323 | -0.1182 | -0.1002 | 100.00 |
| Compact | 2 | Green connectivity–interspersion score (G3) | 201 | -0.0085 | -0.0002 | 0.0171 | 0.00 |
| Compact | 2 | Grey connectivity–interspersion score (B3) | 201 | -0.0657 | -0.0461 | -0.0245 | 17.41 |
| Compact | 2 | Green Bridge proportion | 201 | -0.0668 | -0.0531 | -0.0238 | 40.80 |
| Compact | 2 | Grey Bridge proportion | 201 | -0.1069 | -0.0906 | -0.0399 | 66.67 |
| Compact | 3 | Mean building height | 391 | -0.0025 | 0.0158 | 0.0307 | 0.26 |
| Compact | 3 | Grid-mean canopy height | 391 | -0.1117 | -0.0772 | 0.0281 | 87.21 |
| Compact | 3 | Green-quantity score (G1) | 391 | -0.8106 | -0.7843 | -0.6982 | 100.00 |
| Compact | 3 | Green fragmentation–extension score (G2) | 391 | -0.1701 | -0.1549 | -0.1261 | 100.00 |
| Compact | 3 | Green connectivity–interspersion score (G3) | 391 | -0.0043 | 0.0091 | 0.0243 | 0.00 |
| Compact | 3 | Grey connectivity–interspersion score (B3) | 391 | -0.0571 | -0.0110 | 0.0086 | 24.30 |
| Compact | 3 | Green Bridge proportion | 391 | -0.0546 | -0.0328 | -0.0010 | 26.85 |
| Compact | 3 | Grey Bridge proportion | 391 | -0.0720 | -0.0553 | -0.0404 | 48.59 |
| Open mid-/high-rise | 1 | Mean building height | 265 | 0.0738 | 0.1162 | 0.1789 | 84.15 |
| Open mid-/high-rise | 1 | Grid-mean canopy height | 265 | -0.0434 | -0.0188 | 0.0782 | 51.70 |
| Open mid-/high-rise | 1 | Green-quantity score (G1) | 265 | -0.5594 | -0.5463 | -0.5281 | 100.00 |
| Open mid-/high-rise | 1 | Green fragmentation–extension score (G2) | 265 | -0.1711 | -0.1418 | -0.1346 | 100.00 |
| Open mid-/high-rise | 1 | Green connectivity–interspersion score (G3) | 265 | -0.0315 | -0.0133 | -0.0045 | 1.13 |
| Open mid-/high-rise | 1 | Grey connectivity–interspersion score (B3) | 265 | -0.0730 | -0.0659 | -0.0445 | 60.75 |
| Open mid-/high-rise | 1 | Green Bridge proportion | 265 | -0.0757 | -0.0673 | -0.0548 | 75.85 |
| Open mid-/high-rise | 1 | Grey Bridge proportion | 265 | -0.0191 | -0.0065 | 0.0133 | 0.75 |
| Open mid-/high-rise | 2 | Mean building height | 306 | -0.0084 | 0.0146 | 0.0500 | 18.95 |
| Open mid-/high-rise | 2 | Grid-mean canopy height | 306 | 0.0176 | 0.0735 | 0.1064 | 58.82 |
| Open mid-/high-rise | 2 | Green-quantity score (G1) | 306 | -0.6612 | -0.6086 | -0.5867 | 100.00 |
| Open mid-/high-rise | 2 | Green fragmentation–extension score (G2) | 306 | -0.1655 | -0.1314 | -0.1082 | 100.00 |
| Open mid-/high-rise | 2 | Green connectivity–interspersion score (G3) | 306 | -0.0096 | 0.0017 | 0.0374 | 0.00 |
| Open mid-/high-rise | 2 | Grey connectivity–interspersion score (B3) | 306 | -0.0794 | -0.0718 | -0.0544 | 49.35 |
| Open mid-/high-rise | 2 | Green Bridge proportion | 306 | -0.0725 | -0.0332 | 0.0153 | 38.56 |
| Open mid-/high-rise | 2 | Grey Bridge proportion | 306 | -0.0438 | -0.0331 | -0.0123 | 14.71 |
| Open mid-/high-rise | 3 | Mean building height | 488 | -0.0070 | 0.0080 | 0.0323 | 2.87 |
| Open mid-/high-rise | 3 | Grid-mean canopy height | 488 | -0.1342 | -0.0656 | 0.0656 | 83.40 |
| Open mid-/high-rise | 3 | Green-quantity score (G1) | 488 | -0.7994 | -0.7607 | -0.6542 | 100.00 |
| Open mid-/high-rise | 3 | Green fragmentation–extension score (G2) | 488 | -0.1874 | -0.1628 | -0.1200 | 100.00 |
| Open mid-/high-rise | 3 | Green connectivity–interspersion score (G3) | 488 | -0.0051 | 0.0217 | 0.0383 | 0.00 |
| Open mid-/high-rise | 3 | Grey connectivity–interspersion score (B3) | 488 | -0.0782 | -0.0196 | 0.0048 | 31.97 |
| Open mid-/high-rise | 3 | Green Bridge proportion | 488 | -0.0567 | -0.0176 | 0.0262 | 37.30 |
| Open mid-/high-rise | 3 | Grey Bridge proportion | 488 | -0.0562 | -0.0440 | -0.0319 | 22.95 |
| Open low-rise | 1 | Mean building height | 279 | 0.0961 | 0.1566 | 0.2143 | 91.04 |
| Open low-rise | 1 | Grid-mean canopy height | 279 | -0.0516 | -0.0234 | 0.0895 | 58.06 |
| Open low-rise | 1 | Green-quantity score (G1) | 279 | -0.5676 | -0.5519 | -0.5417 | 100.00 |
| Open low-rise | 1 | Green fragmentation–extension score (G2) | 279 | -0.1768 | -0.1515 | -0.1369 | 100.00 |
| Open low-rise | 1 | Green connectivity–interspersion score (G3) | 279 | -0.0366 | -0.0272 | -0.0115 | 1.79 |
| Open low-rise | 1 | Grey connectivity–interspersion score (B3) | 279 | -0.0723 | -0.0572 | -0.0407 | 52.33 |
| Open low-rise | 1 | Green Bridge proportion | 279 | -0.0810 | -0.0654 | -0.0450 | 73.12 |
| Open low-rise | 1 | Grey Bridge proportion | 279 | -0.0141 | 0.0006 | 0.0138 | 0.00 |
| Open low-rise | 2 | Mean building height | 212 | 0.0093 | 0.0585 | 0.0955 | 44.34 |
| Open low-rise | 2 | Grid-mean canopy height | 212 | 0.0493 | 0.0873 | 0.2283 | 57.08 |
| Open low-rise | 2 | Green-quantity score (G1) | 212 | -0.6222 | -0.5905 | -0.5688 | 100.00 |
| Open low-rise | 2 | Green fragmentation–extension score (G2) | 212 | -0.1896 | -0.1685 | -0.1367 | 100.00 |
| Open low-rise | 2 | Green connectivity–interspersion score (G3) | 212 | -0.0344 | -0.0039 | 0.0468 | 0.94 |
| Open low-rise | 2 | Grey connectivity–interspersion score (B3) | 212 | -0.0833 | -0.0742 | -0.0563 | 55.66 |
| Open low-rise | 2 | Green Bridge proportion | 212 | -0.0773 | -0.0254 | 0.0293 | 35.85 |
| Open low-rise | 2 | Grey Bridge proportion | 212 | -0.0333 | -0.0205 | 0.0056 | 6.13 |
| Open low-rise | 3 | Mean building height | 169 | -0.0196 | 0.0040 | 0.0478 | 11.24 |
| Open low-rise | 3 | Grid-mean canopy height | 169 | -0.1503 | -0.1292 | -0.0317 | 88.76 |
| Open low-rise | 3 | Green-quantity score (G1) | 169 | -0.7923 | -0.7745 | -0.6975 | 100.00 |
| Open low-rise | 3 | Green fragmentation–extension score (G2) | 169 | -0.2088 | -0.1854 | -0.1696 | 100.00 |
| Open low-rise | 3 | Green connectivity–interspersion score (G3) | 169 | 0.0248 | 0.0416 | 0.0513 | 0.00 |
| Open low-rise | 3 | Grey connectivity–interspersion score (B3) | 169 | -0.0396 | -0.0064 | 0.0016 | 17.75 |
| Open low-rise | 3 | Green Bridge proportion | 169 | -0.0279 | 0.0028 | 0.0693 | 46.75 |
| Open low-rise | 3 | Grey Bridge proportion | 169 | -0.0516 | -0.0341 | -0.0252 | 8.88 |
| Green-space type | 1 | Mean building height | 955 | 0.1018 | 0.1576 | 0.2504 | 86.81 |
| Green-space type | 1 | Grid-mean canopy height | 955 | -0.0603 | 0.0017 | 0.1391 | 72.46 |
| Green-space type | 1 | Green-quantity score (G1) | 955 | -0.5783 | -0.5572 | -0.5473 | 100.00 |
| Green-space type | 1 | Green fragmentation–extension score (G2) | 955 | -0.1797 | -0.1659 | -0.1386 | 100.00 |
| Green-space type | 1 | Green connectivity–interspersion score (G3) | 955 | -0.0415 | -0.0324 | -0.0075 | 3.04 |
| Green-space type | 1 | Grey connectivity–interspersion score (B3) | 955 | -0.0700 | -0.0477 | -0.0319 | 35.39 |
| Green-space type | 1 | Green Bridge proportion | 955 | -0.0778 | -0.0610 | 0.0216 | 61.57 |
| Green-space type | 1 | Grey Bridge proportion | 955 | -0.0055 | 0.0123 | 0.0225 | 0.00 |
| Green-space type | 2 | Mean building height | 488 | 0.0103 | 0.0532 | 0.0933 | 43.85 |
| Green-space type | 2 | Grid-mean canopy height | 488 | 0.0476 | 0.0825 | 0.2533 | 55.74 |
| Green-space type | 2 | Green-quantity score (G1) | 488 | -0.5972 | -0.5767 | -0.5622 | 100.00 |
| Green-space type | 2 | Green fragmentation–extension score (G2) | 488 | -0.1881 | -0.1705 | -0.1512 | 100.00 |
| Green-space type | 2 | Green connectivity–interspersion score (G3) | 488 | -0.0246 | 0.0166 | 0.0481 | 1.23 |
| Green-space type | 2 | Grey connectivity–interspersion score (B3) | 488 | -0.0797 | -0.0730 | -0.0541 | 51.43 |
| Green-space type | 2 | Green Bridge proportion | 488 | -0.0390 | 0.0147 | 0.0350 | 20.49 |
| Green-space type | 2 | Grey Bridge proportion | 488 | -0.0235 | -0.0055 | 0.0103 | 0.20 |
| Green-space type | 3 | Mean building height | 197 | -0.0139 | 0.0051 | 0.0432 | 6.09 |
| Green-space type | 3 | Grid-mean canopy height | 197 | -0.1471 | -0.1276 | 0.0706 | 83.25 |
| Green-space type | 3 | Green-quantity score (G1) | 197 | -0.7929 | -0.7535 | -0.6343 | 100.00 |
| Green-space type | 3 | Green fragmentation–extension score (G2) | 197 | -0.1993 | -0.1859 | -0.1578 | 100.00 |
| Green-space type | 3 | Green connectivity–interspersion score (G3) | 197 | 0.0151 | 0.0438 | 0.0525 | 0.00 |
| Green-space type | 3 | Grey connectivity–interspersion score (B3) | 197 | -0.0825 | -0.0160 | 0.0028 | 26.40 |
| Green-space type | 3 | Green Bridge proportion | 197 | -0.0262 | 0.0027 | 0.0567 | 32.49 |
| Green-space type | 3 | Grey Bridge proportion | 197 | -0.0471 | -0.0349 | -0.0266 | 1.02 |

Note. There are 96 indicator-group records. Coefficient summaries include all units in each group; the percentage carrying the software-corrected significance flag is reported separately. Coefficients are signed values from the scaled model. Complete quantiles, means, and SDs are provided in `TableS6b_scaled_coefficient_profiles.csv`.

**Supplementary Table S6c. Full class orders of indicator and coefficient medians within each morphology.**

| Morphology | Indicator | Indicator medians, ascending order | Coefficient medians, ascending order |
| --- | --- | --- | --- |
| Compact | Mean building height | 1<2<3 | 2<3<1 |
| Open mid-/high-rise | Mean building height | 1<2<3 | 3<2<1 |
| Open low-rise | Mean building height | 1<2<3 | 3<2<1 |
| Green-space type | Mean building height | 1<3<2 | 3<2<1 |
| Compact | Grid-mean canopy height | 1=2=3 | 3<1<2 |
| Open mid-/high-rise | Grid-mean canopy height | 1=2=3 | 3<1<2 |
| Open low-rise | Grid-mean canopy height | 1=2=3 | 3<1<2 |
| Green-space type | Grid-mean canopy height | 1=2=3 | 3<1<2 |
| Compact | Green-quantity score (G1) | 2=3<1 | 3<2<1 |
| Open mid-/high-rise | Green-quantity score (G1) | 3<2<1 | 3<2<1 |
| Open low-rise | Green-quantity score (G1) | 3<2<1 | 3<2<1 |
| Green-space type | Green-quantity score (G1) | 3<2<1 | 3<2<1 |
| Compact | Green fragmentation–extension score (G2) | 2=3<1 | 3<1<2 |
| Open mid-/high-rise | Green fragmentation–extension score (G2) | 1<2<3 | 3<1<2 |
| Open low-rise | Green fragmentation–extension score (G2) | 1<2<3 | 3<2<1 |
| Green-space type | Green fragmentation–extension score (G2) | 1<2<3 | 3<2<1 |
| Compact | Green connectivity–interspersion score (G3) | 2=3<1 | 1<2<3 |
| Open mid-/high-rise | Green connectivity–interspersion score (G3) | 3<2<1 | 1<2<3 |
| Open low-rise | Green connectivity–interspersion score (G3) | 2<3<1 | 1<2<3 |
| Green-space type | Green connectivity–interspersion score (G3) | 2<3<1 | 1<2<3 |
| Compact | Grey connectivity–interspersion score (B3) | 1<2=3 | 1<2<3 |
| Open mid-/high-rise | Grey connectivity–interspersion score (B3) | 1<2<3 | 2<1<3 |
| Open low-rise | Grey connectivity–interspersion score (B3) | 2<1<3 | 2<1<3 |
| Green-space type | Grey connectivity–interspersion score (B3) | 3<2<1 | 2<1<3 |
| Compact | Green Bridge proportion | 1=2=3 | 1<2<3 |
| Open mid-/high-rise | Green Bridge proportion | 2=3<1 | 1<2<3 |
| Open low-rise | Green Bridge proportion | 3<1<2 | 1<2<3 |
| Green-space type | Green Bridge proportion | 1<3<2 | 1<3<2 |
| Compact | Grey Bridge proportion | 1=2=3 | 2<3<1 |
| Open mid-/high-rise | Grey Bridge proportion | 1=3<2 | 3<2<1 |
| Open low-rise | Grey Bridge proportion | 1<2<3 | 3<2<1 |
| Green-space type | Grey Bridge proportion | 1=2<3 | 3<2<1 |

Note. Classes 1, 2, and 3 denote lower, intermediate, and higher local fit, respectively. “<” orders the corresponding medians from low to high, and “=” denotes exact ties. A complete class order and a shared extreme class are distinct summaries.

**Supplementary Table S6d. Cross-morphology comparison of complete median orders.**

| Indicator | Same full indicator order across four morphologies | Distinct indicator orders | Same full coefficient order across four morphologies | Distinct coefficient orders |
| --- | --- | --- | --- | --- |
| Mean building height | No | 1<2<3;1<3<2 | No | 2<3<1;3<2<1 |
| Grid-mean canopy height | Yes | 1=2=3 | Yes | 3<1<2 |
| Green-quantity score (G1) | No | 2=3<1;3<2<1 | Yes | 3<2<1 |
| Green fragmentation–extension score (G2) | No | 1<2<3;2=3<1 | No | 3<1<2;3<2<1 |
| Green connectivity–interspersion score (G3) | No | 2<3<1;2=3<1;3<2<1 | Yes | 1<2<3 |
| Grey connectivity–interspersion score (B3) | No | 1<2<3;1<2=3;2<1<3;3<2<1 | No | 1<2<3;2<1<3 |
| Green Bridge proportion | No | 1<3<2;1=2=3;2=3<1;3<1<2 | No | 1<2<3;1<3<2 |
| Grey Bridge proportion | No | 1<2<3;1=2<3;1=2=3;1=3<2 | No | 2<3<1;3<2<1 |

Note. A common complete order requires agreement across all four morphologies. All distinct orders are retained; a shared endpoint alone is not classified as agreement in the complete order.

**Supplementary Table S6e. Overlap of interquartile ranges between local-fit classes.**

| Indicator | Quantity compared | Class pairs compared | Pairs with overlapping IQRs |
| --- | --- | --- | --- |
| Mean building height | Within-morphology relative indicator level | 12 | 12 |
| Mean building height | Scaled-model local coefficient | 12 | 4 |
| Grid-mean canopy height | Within-morphology relative indicator level | 12 | 12 |
| Grid-mean canopy height | Scaled-model local coefficient | 12 | 11 |
| Green-quantity score (G1) | Within-morphology relative indicator level | 12 | 12 |
| Green-quantity score (G1) | Scaled-model local coefficient | 12 | 3 |
| Green fragmentation–extension score (G2) | Within-morphology relative indicator level | 12 | 12 |
| Green fragmentation–extension score (G2) | Scaled-model local coefficient | 12 | 12 |
| Green connectivity–interspersion score (G3) | Within-morphology relative indicator level | 12 | 12 |
| Green connectivity–interspersion score (G3) | Scaled-model local coefficient | 12 | 9 |
| Grey connectivity–interspersion score (B3) | Within-morphology relative indicator level | 12 | 12 |
| Grey connectivity–interspersion score (B3) | Scaled-model local coefficient | 12 | 10 |
| Green Bridge proportion | Within-morphology relative indicator level | 12 | 12 |
| Green Bridge proportion | Scaled-model local coefficient | 12 | 10 |
| Grey Bridge proportion | Within-morphology relative indicator level | 12 | 12 |
| Grey Bridge proportion | Scaled-model local coefficient | 12 | 6 |

Note. For each indicator, three local-fit class pairs are compared within each of four morphologies, giving 12 pairs. The table counts pairs whose interquartile intervals overlap.

**Supplementary Table S6f. Classes with minimum and maximum medians under the three-class local-fit zoning.**

| Indicator | Morphology | Quantity compared | Class with minimum median | Class with maximum median |
| --- | --- | --- | --- | --- |
| Mean building height | Compact | Within-morphology relative indicator level | 1 | 3 |
| Mean building height | Compact | Scaled-model local coefficient | 2 | 1 |
| Mean building height | Open mid-/high-rise | Within-morphology relative indicator level | 1 | 3 |
| Mean building height | Open mid-/high-rise | Scaled-model local coefficient | 3 | 1 |
| Mean building height | Open low-rise | Within-morphology relative indicator level | 1 | 3 |
| Mean building height | Open low-rise | Scaled-model local coefficient | 3 | 1 |
| Mean building height | Green-space type | Within-morphology relative indicator level | 1 | 2 |
| Mean building height | Green-space type | Scaled-model local coefficient | 3 | 1 |
| Grid-mean canopy height | Compact | Within-morphology relative indicator level | 1=2=3 | 1=2=3 |
| Grid-mean canopy height | Compact | Scaled-model local coefficient | 3 | 2 |
| Grid-mean canopy height | Open mid-/high-rise | Within-morphology relative indicator level | 1=2=3 | 1=2=3 |
| Grid-mean canopy height | Open mid-/high-rise | Scaled-model local coefficient | 3 | 2 |
| Grid-mean canopy height | Open low-rise | Within-morphology relative indicator level | 1=2=3 | 1=2=3 |
| Grid-mean canopy height | Open low-rise | Scaled-model local coefficient | 3 | 2 |
| Grid-mean canopy height | Green-space type | Within-morphology relative indicator level | 1=2=3 | 1=2=3 |
| Grid-mean canopy height | Green-space type | Scaled-model local coefficient | 3 | 2 |
| Green-quantity score (G1) | Compact | Within-morphology relative indicator level | 2=3 | 1 |
| Green-quantity score (G1) | Compact | Scaled-model local coefficient | 3 | 1 |
| Green-quantity score (G1) | Open mid-/high-rise | Within-morphology relative indicator level | 3 | 1 |
| Green-quantity score (G1) | Open mid-/high-rise | Scaled-model local coefficient | 3 | 1 |
| Green-quantity score (G1) | Open low-rise | Within-morphology relative indicator level | 3 | 1 |
| Green-quantity score (G1) | Open low-rise | Scaled-model local coefficient | 3 | 1 |
| Green-quantity score (G1) | Green-space type | Within-morphology relative indicator level | 3 | 1 |
| Green-quantity score (G1) | Green-space type | Scaled-model local coefficient | 3 | 1 |
| Green fragmentation–extension score (G2) | Compact | Within-morphology relative indicator level | 2=3 | 1 |
| Green fragmentation–extension score (G2) | Compact | Scaled-model local coefficient | 3 | 2 |
| Green fragmentation–extension score (G2) | Open mid-/high-rise | Within-morphology relative indicator level | 1 | 3 |
| Green fragmentation–extension score (G2) | Open mid-/high-rise | Scaled-model local coefficient | 3 | 2 |
| Green fragmentation–extension score (G2) | Open low-rise | Within-morphology relative indicator level | 1 | 3 |
| Green fragmentation–extension score (G2) | Open low-rise | Scaled-model local coefficient | 3 | 1 |
| Green fragmentation–extension score (G2) | Green-space type | Within-morphology relative indicator level | 1 | 3 |
| Green fragmentation–extension score (G2) | Green-space type | Scaled-model local coefficient | 3 | 1 |
| Green connectivity–interspersion score (G3) | Compact | Within-morphology relative indicator level | 2=3 | 1 |
| Green connectivity–interspersion score (G3) | Compact | Scaled-model local coefficient | 1 | 3 |
| Green connectivity–interspersion score (G3) | Open mid-/high-rise | Within-morphology relative indicator level | 3 | 1 |
| Green connectivity–interspersion score (G3) | Open mid-/high-rise | Scaled-model local coefficient | 1 | 3 |
| Green connectivity–interspersion score (G3) | Open low-rise | Within-morphology relative indicator level | 2 | 1 |
| Green connectivity–interspersion score (G3) | Open low-rise | Scaled-model local coefficient | 1 | 3 |
| Green connectivity–interspersion score (G3) | Green-space type | Within-morphology relative indicator level | 2 | 1 |
| Green connectivity–interspersion score (G3) | Green-space type | Scaled-model local coefficient | 1 | 3 |
| Grey connectivity–interspersion score (B3) | Compact | Within-morphology relative indicator level | 1 | 2=3 |
| Grey connectivity–interspersion score (B3) | Compact | Scaled-model local coefficient | 1 | 3 |
| Grey connectivity–interspersion score (B3) | Open mid-/high-rise | Within-morphology relative indicator level | 1 | 3 |
| Grey connectivity–interspersion score (B3) | Open mid-/high-rise | Scaled-model local coefficient | 2 | 3 |
| Grey connectivity–interspersion score (B3) | Open low-rise | Within-morphology relative indicator level | 2 | 3 |
| Grey connectivity–interspersion score (B3) | Open low-rise | Scaled-model local coefficient | 2 | 3 |
| Grey connectivity–interspersion score (B3) | Green-space type | Within-morphology relative indicator level | 3 | 1 |
| Grey connectivity–interspersion score (B3) | Green-space type | Scaled-model local coefficient | 2 | 3 |
| Green Bridge proportion | Compact | Within-morphology relative indicator level | 1=2=3 | 1=2=3 |
| Green Bridge proportion | Compact | Scaled-model local coefficient | 1 | 3 |
| Green Bridge proportion | Open mid-/high-rise | Within-morphology relative indicator level | 2=3 | 1 |
| Green Bridge proportion | Open mid-/high-rise | Scaled-model local coefficient | 1 | 3 |
| Green Bridge proportion | Open low-rise | Within-morphology relative indicator level | 3 | 2 |
| Green Bridge proportion | Open low-rise | Scaled-model local coefficient | 1 | 3 |
| Green Bridge proportion | Green-space type | Within-morphology relative indicator level | 1 | 2 |
| Green Bridge proportion | Green-space type | Scaled-model local coefficient | 1 | 2 |
| Grey Bridge proportion | Compact | Within-morphology relative indicator level | 1=2=3 | 1=2=3 |
| Grey Bridge proportion | Compact | Scaled-model local coefficient | 2 | 1 |
| Grey Bridge proportion | Open mid-/high-rise | Within-morphology relative indicator level | 1=3 | 2 |
| Grey Bridge proportion | Open mid-/high-rise | Scaled-model local coefficient | 3 | 1 |
| Grey Bridge proportion | Open low-rise | Within-morphology relative indicator level | 1 | 3 |
| Grey Bridge proportion | Open low-rise | Scaled-model local coefficient | 3 | 1 |
| Grey Bridge proportion | Green-space type | Within-morphology relative indicator level | 1=2 | 3 |
| Grey Bridge proportion | Green-space type | Scaled-model local coefficient | 3 | 1 |

Note. All classes tied at an endpoint are retained. Shared endpoint classes do not imply the same complete order of intermediate classes, coefficient magnitudes, or unranked indicator values.

**Supplementary Table S7. Exact classification rules for seven basic morphologies and their four-class mapping.**

| Basic morphology class | Building density, mean height, and green-cover conditions | Four-class morphology |
| --- | --- | --- |
| Compact high-rise | $BD>20\%$; $H>22$ m | Compact |
| Compact mid-rise | $BD>20\%$; $11\leq H\leq22$ m | Compact |
| Compact low-rise | $BD>20\%$; $H<11$ m | Compact |
| Open high-rise | $BD\leq20\%$; $H>22$ m | Open mid-/high-rise |
| Open mid-rise | $BD\leq20\%$; $11\leq H\leq22$ m | Open mid-/high-rise |
| Open low-rise | $BD\leq20\%$; $H<11$ m; $GC\leq50\%$ | Open low-rise |
| Green-space type | $BD\leq20\%$; $H<11$ m; $GC>50\%$ | Green-space type |

Note. BD, building density; H, mean building height; GC, green-cover percentage. The classification thresholds used here are 20%, 11 m, 22 m, and 50%.

## Supplementary Table S8. Joint thermal conditions and coefficient comparisons

Tables S8a–f provide exact values supporting the same-grid comparison of observed thermal conditions and existing MGWR coefficients in Figures 11 and 12. Table S8b gives the exact conditions of the eight joint sets outlined in Figure 11e–h and summarised in Figure 12; Table S8e reports their original local-fit composition, and Table S8f reports sector-specific cool/hot-tail proportions. The original four morphologies and three local-fit classes are unchanged. The quartiles and fixed coordinate sectors are descriptive summaries. They do not constitute additional fitted models or independent validations.

**Supplementary Table S8a. Within-morphology quartile thresholds for PWP and the local G1 coefficient.**

| Morphology | Variable | n | q25 | q50 | q75 |
| --- | --- | --- | --- | --- | --- |
| Compact | PWP (°C) | 646 | 33.852 | 34.795 | 35.423 |
| Compact | G1 coefficient | 646 | -0.800 | -0.756 | -0.665 |
| Open mid-/high-rise | PWP (°C) | 1059 | 32.095 | 33.052 | 34.038 |
| Open mid-/high-rise | G1 coefficient | 1059 | -0.760 | -0.638 | -0.572 |
| Open low-rise | PWP (°C) | 660 | 31.658 | 32.192 | 32.826 |
| Open low-rise | G1 coefficient | 660 | -0.648 | -0.582 | -0.555 |
| Green-space type | PWP (°C) | 1640 | 30.990 | 31.531 | 32.053 |
| Green-space type | G1 coefficient | 1640 | -0.594 | -0.570 | -0.553 |

Notes: PWP is total-population-weighted summer daytime land-surface temperature. G1 is the Min–Max-scaled green-quantity score, z(G_CA), derived from green class area. Its local coefficient is the signed coefficient from the scaled MGWR model, in which the dependent and explanatory variables were standardised to mean zero and standard deviation one. Each variable is divided separately within each morphology: Q1 ≤ q25; Q2 = (q25, q50]; Q3 = (q50, q75]; Q4 > q75. PWP Q1 and Q4 denote the lowest and highest PWP quartile intervals of that morphology, respectively. Coefficient Q1 denotes its lowest signed-coefficient quartile interval. Quartile labels do not imply common absolute thresholds across morphologies. Thresholds are rounded here; assignment used the unrounded values in the linked source data. n is the number of grid cells. Quantiles use linear interpolation; equal values are kept together.


**Supplementary Table S8b. Actual grid conditions at the cool and hot PWP tails within the lowest signed G1-coefficient quartile interval.**

| Morphology | PWP tail | Joint n/N (%) | G1, median [IQR] | Height (m), median [IQR] | PWP median (°C) |
| --- | --- | --- | --- | --- | --- |
| Compact | Coolest (Q1) | 23/162 (14.2%) | 0.005 [0.000, 0.055] | 16.25 [11.57, 17.19] | 33.26 |
| Compact | Hottest (Q4) | 75/162 (46.3%) | 0.000 [0.000, 0.000] | 19.10 [17.31, 20.86] | 35.78 |
| Open mid-/high-rise | Coolest (Q1) | 65/265 (24.5%) | 0.458 [0.261, 0.718] | 12.97 [11.64, 15.57] | 31.11 |
| Open mid-/high-rise | Hottest (Q4) | 91/265 (34.3%) | 0.000 [0.000, 0.027] | 17.70 [15.59, 20.95] | 34.83 |
| Open low-rise | Coolest (Q1) | 31/165 (18.8%) | 0.343 [0.278, 0.397] | 8.75 [7.99, 9.74] | 31.13 |
| Open low-rise | Hottest (Q4) | 62/165 (37.6%) | 0.175 [0.060, 0.354] | 9.68 [9.08, 10.28] | 33.57 |
| Green-space type | Coolest (Q1) | 179/410 (43.7%) | 0.761 [0.628, 0.875] | 8.00 [7.63, 8.72] | 30.27 |
| Green-space type | Hottest (Q4) | 90/410 (22.0%) | 0.669 [0.601, 0.782] | 8.86 [8.28, 9.92] | 32.49 |

Notes: Every row contains the same grid cells satisfying both the indicated PWP quartile and coefficient Q1 from Table S8a. The fraction is joint n divided by all grid cells in that morphology-specific PWP quartile (N); the percentage uses N as its denominator. G1 and building height are medians [q25, q75] for those joint grid sets. PWP is the median for the same set. G1 is the dimensionless Min–Max-scaled green-quantity score, not green-cover percentage. Intervals describe the observed distribution, not confidence intervals. The eight rows include both PWP tails in all four morphologies. The complete 64-cell table retains all PWP–coefficient quartile combinations, their coefficient distributions and geographic counts in the source data. Coefficient distributions and all grid counts are retained without a minimum-n exclusion.


**Supplementary Table S8c. Within-morphology association between PWP and the local G1 coefficient by fixed coordinate sector.**

| Morphology | NW: ρ (n) | NE: ρ (n) | SW: ρ (n) | SE: ρ (n) |
| --- | --- | --- | --- | --- |
| Compact | -0.352 (330) | -0.386 (94) | -0.609 (172) | -0.495 (50) |
| Open mid-/high-rise | +0.034 (297) | -0.101 (335) | -0.452 (271) | -0.462 (156) |
| Open low-rise | +0.028 (109) | +0.207 (243) | -0.027 (168) | +0.070 (140) |
| Green-space type | +0.448 (125) | +0.447 (578) | -0.110 (444) | +0.369 (493) |

Notes: Cells show Spearman's ρ (n grid cells), calculated from same-grid PWP and signed scaled local G1-coefficient values. The four descriptive sectors use the midpoints of the full grid-centroid bounding box: X = 458874.0841 m and Y = 4413648.5752 m in EPSG:32650. East and north include values equal to their respective midpoints. NW, NE, SW and SE indicate northwest, northeast, southwest and southeast. The boundaries were fixed from coordinates and do not constitute new morphology or local-fit classes. Correlations are descriptive; no independence-based p values or confidence intervals are reported for these spatially dependent model outputs.


**Supplementary Table S8d. Uniform comparison of complete coefficient orders and common endpoints across the four morphologies.**

| Indicator | Common complete order | Common minimum | Common maximum |
| --- | --- | --- | --- |
| Mean building height | Not shared | None | L |
| Grid-mean canopy height | H<L<M | H | M |
| Green quantity (G1) | H<M<L | H | L |
| Green fragmentation–extension (G2) | Not shared | H | None |
| Green connectivity–interspersion (G3) | L<M<H | L | H |
| Grey connectivity–interspersion (B3) | Not shared | None | H |
| Green Bridge proportion | Not shared | L | None |
| Grey Bridge proportion | Not shared | None | L |

Notes: L, M and H denote the existing lower-, intermediate- and higher-fit classes. Orders are ascending signed medians, not absolute coefficient magnitudes. A complete order is shared only when all three local-fit class medians have the same order in all four morphologies. A common minimum or maximum requires the same endpoint class in all four morphologies. “None” means that no endpoint class is common to all four, not that the coefficient is zero. The same criterion is applied to all eight retained indicators. This table describes median orders and does not retest the original coefficient significance flags. The unrounded within-morphology medians and orders are retained in the source data.


**Supplementary Table S8e. Original local-fit class composition of the joint PWP-tail and most-negative G1-coefficient sets.**

| Morphology | PWP tail | Joint n | Lower fit, n (%) | Intermediate fit, n (%) | Higher fit, n (%) |
| --- | --- | --- | --- | --- | --- |
| Compact | Coolest (Q1) | 23 | 0 (0.0%) | 0 (0.0%) | 23 (100.0%) |
| Compact | Hottest (Q4) | 75 | 0 (0.0%) | 17 (22.7%) | 58 (77.3%) |
| Open mid-/high-rise | Coolest (Q1) | 65 | 0 (0.0%) | 0 (0.0%) | 65 (100.0%) |
| Open mid-/high-rise | Hottest (Q4) | 91 | 2 (2.2%) | 17 (18.7%) | 72 (79.1%) |
| Open low-rise | Coolest (Q1) | 31 | 0 (0.0%) | 0 (0.0%) | 31 (100.0%) |
| Open low-rise | Hottest (Q4) | 62 | 0 (0.0%) | 16 (25.8%) | 46 (74.2%) |
| Green-space type | Coolest (Q1) | 179 | 63 (35.2%) | 51 (28.5%) | 65 (36.3%) |
| Green-space type | Hottest (Q4) | 90 | 1 (1.1%) | 31 (34.4%) | 58 (64.4%) |

Notes: Each joint set contains grid cells assigned both the indicated PWP tail and G1-coefficient Q1 (the lowest signed-coefficient quartile interval). Quartiles were defined across all cells within each morphology, not recalculated within sectors or fit classes; definitions and thresholds are in Table S8a. The three columns retain the original lower, intermediate and higher Local R-squared classes (LR2_ZONE 1, 2 and 3), with unchanged boundaries. Each percentage uses the row's joint n as its denominator, and the three counts sum to that n. This differs from the PWP-tail denominators in Table S8b. All eight joint sets are retained. Counts are descriptive; no new classification or significance test was introduced.

**Supplementary Table S8f. Sector-specific proportions of the cool and hot PWP tails in the lowest signed G1-coefficient quartile interval.**

| Morphology | Sector | Coolest PWP quartile interval: n/N (%) | Hottest PWP quartile interval: n/N (%) |
| --- | --- | --- | --- |
| Compact | NW | 23/64 (35.9%) | 72/109 (66.1%) |
| Compact | NE | 0/44 (0.0%) | 0/4 (0.0%) |
| Compact | SW | 0/38 (0.0%) | 3/46 (6.5%) |
| Compact | SE | 0/16 (0.0%) | 0/3 (0.0%) |
| Open mid-/high-rise | NW | 55/66 (83.3%) | 58/91 (63.7%) |
| Open mid-/high-rise | NE | 0/111 (0.0%) | 0/71 (0.0%) |
| Open mid-/high-rise | SW | 10/30 (33.3%) | 33/82 (40.2%) |
| Open mid-/high-rise | SE | 0/58 (0.0%) | 0/21 (0.0%) |
| Open low-rise | NW | 18/24 (75.0%) | 24/26 (92.3%) |
| Open low-rise | NE | 0/75 (0.0%) | 6/44 (13.6%) |
| Open low-rise | SW | 13/17 (76.5%) | 25/76 (32.9%) |
| Open low-rise | SE | 0/49 (0.0%) | 7/19 (36.8%) |
| Green-space type | NW | 45/55 (81.8%) | 21/24 (87.5%) |
| Green-space type | NE | 44/217 (20.3%) | 11/74 (14.9%) |
| Green-space type | SW | 12/21 (57.1%) | 39/202 (19.3%) |
| Green-space type | SE | 78/117 (66.7%) | 19/110 (17.3%) |

Notes: n counts cells in the indicated morphology and sector assigned both the PWP tail and G1-coefficient Q1 (the lowest signed-coefficient quartile interval). N counts all cells in that morphology-specific PWP tail within the same sector, irrespective of coefficient quartile. Percentages are 100 n/N, not each sector's share of the selected joint set. Quartiles retain the whole-morphology definitions in Table S8a and were not recalculated within sectors. The fixed NW, NE, SW and SE definitions are given in Table S8c. All 16 morphology-sector combinations and both tails are retained, including small denominators and zero joint counts. Existing morphology and fit classifications remain unchanged. Counts are descriptive.

The complete machine-readable data are described in `Data_S8/Data_guide.md`.

**Supplementary Table S9a. Within-morphology thermal-tail overlaps with the lowest G1-coefficient quartile interval in the two existing MGWR outputs.**

| Morphology | PWP tail | Tail denominator | Joint n, 1,400 | Overlap, 1,400 (%) | Joint n, 1,600 | Overlap, 1,600 (%) | Change, 1,600 − 1,400 (percentage points) |
| --- | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Compact | Cool | 162 | 32 | 19.8 | 23 | 14.2 | -5.56 |
| Compact | Hot | 162 | 66 | 40.7 | 75 | 46.3 | 5.56 |
| Open mid-/high-rise | Cool | 265 | 65 | 24.5 | 65 | 24.5 | 0.00 |
| Open mid-/high-rise | Hot | 265 | 88 | 33.2 | 91 | 34.3 | 1.13 |
| Open low-rise | Cool | 165 | 32 | 19.4 | 31 | 18.8 | -0.61 |
| Open low-rise | Hot | 165 | 59 | 35.8 | 62 | 37.6 | 1.82 |
| Green-space type | Cool | 410 | 186 | 45.4 | 179 | 43.7 | -1.71 |
| Green-space type | Hot | 410 | 83 | 20.2 | 90 | 22.0 | 1.71 |

Note. The response, morphology membership, PWP quartile thresholds and PWP-tail denominators are fixed across runs. The lowest signed G1-coefficient quartile interval is determined separately for each morphology and each run. Quantiles use linear interpolation, h = (n − 1)q, with boundary values assigned to the lower interval and tied values kept together. Each percentage is 100 × the joint count divided by the corresponding morphology-specific PWP-tail count. The main-text values use the 1,600 output. The comparison retains the existing three Local R² categories and does not reclassify local-fit zones.

| Morphology | Hot − cool overlap, 1,400 (percentage points) | Hot − cool overlap, 1,600 (percentage points) | Direction retained |
| --- | ---: | ---: | --- |
| Compact | 20.99 | 32.10 | Yes |
| Open mid-/high-rise | 8.68 | 9.81 | Yes |
| Open low-rise | 16.36 | 18.79 | Yes |
| Green-space type | -25.12 | -21.71 | Yes |

The overall directions are retained in all four morphologies, while individual overlap proportions and their differences change. In compact morphology, the hot-minus-cool difference increases from 20.99 to 32.10 percentage points. This comparison addresses the two existing lower-bound choices, not the separation of physical spatial conditions from smoothing or independent validation.

**Supplementary Table S9b. Changes in membership of the lowest within-morphology G1-coefficient quartile interval.**

| Morphology | All units | Q1 n, 1,400 | Q1 n, 1,600 | Retained in Q1 | Entering Q1 in 1,600 | Leaving Q1 in 1,600 | Total membership changes |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| Compact | 646 | 162 | 162 | 151 | 11 | 11 | 22 |
| Open mid-/high-rise | 1059 | 265 | 265 | 260 | 5 | 5 | 10 |
| Open low-rise | 660 | 165 | 165 | 160 | 5 | 5 | 10 |
| Green-space type | 1640 | 410 | 410 | 392 | 18 | 18 | 36 |
| Total | 4005 | 1002 | 1002 | 963 | 39 | 39 | 78 |

Note. Q1 is a within-morphology coefficient quartile interval, not a shared coefficient threshold across morphologies. A membership change means entering or leaving this interval between the two outputs. Unchanged total Q1 counts do not imply unchanged members. Each changed grid is counted once; 78 is the sum of 39 entries and 39 exits, not the number of exits. Complete grid identities, thresholds and joint counts are supplied in Supplementary Data S9.

# Supplementary data

## Supplementary Data S6. Complete morphology-by-fit indicator and coefficient summaries

The two 96-row files retain all four morphologies, three local-fit classes and eight indicators. `TableS6a_indicator_rank_and_raw_profiles.csv` supports Table S6a, while `TableS6b_scaled_coefficient_profiles.csv` supports Table S6b. Both files supply the complete numerical summaries underlying Figures 9 and 10; field definitions are given in `Data_S6/Data_guide.md`.

## Supplementary Data S8. Complete source data for joint thermal and coefficient comparisons

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
