# Indicator definitions and selection records

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
