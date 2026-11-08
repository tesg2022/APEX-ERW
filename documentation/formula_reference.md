# APEX-ERW Formula and Model Reference

This reference separates formulae encoded in the source analysis from transparent screening calculations added to the dashboard. Where the archive does not provide a complete equation or coefficient set, the dashboard does not claim one is source-validated.

## 1. Source model configuration
The supplied `CIPA_AI_Model_Configuration` records:
- Study area: City of Cape Town, South Africa.
- Intervention: Enhanced Rock Weathering.
- Analysis year: 2025.
- Number of samples: 2,459.
- Number of clusters: 4.
- Predictors: ERA5 and CHIRPS rainfall, evaporation, potential evaporation, temperature, soil moisture, precipitation-minus-evaporation, aridity, runoff, subsurface runoff, elevation, slope, NDVI, NDWI, NDMI, soil pH, SOC, sand percentage, land cover and interaction variables.
- Screening thresholds: pH 4.5–7.5; SOC ≤40 g/kg; slope ≤12°; annual rainfall ≥300 mm; water buffer 500 m.
- `carbon_removal_target_available`: false.

These are source configuration settings, not proof of causal ERW effects.

## 2. Water availability screening
`W = P - ET`
where P is precipitation and ET is actual evapotranspiration, in consistent depth units and periods. This is a climatic water-availability proxy, not groundwater recharge.

## 3. Water balance
`ΔS = P - ET - Q - R`
Use only when terms are consistently defined and non-overlapping. If Q and R represent separate outflows, document each. Do not double-count runoff.

## 4. Weighted environmental index
`EVI = Σ(w_i × X_i)` with `Σw_i = 1`.
The weights, transformations, directionality and missing-data handling must be taken from the actual model implementation. The dashboard does not invent weights.

## 5. Spearman rank correlation
`ρ_s = corr(rank(X), rank(Y))`.
For data without tied ranks, an equivalent expression is `ρ_s = 1 - [6Σd_i² / n(n²-1)]`. The supplied Spearman matrix is displayed as provided.

## 6. Theoretical oxide-based CO₂ capacity
`C_theoretical = (CaO/100 × 44.01/56.077) + (MgO/100 × 44.01/40.304)`
This is an upper-bound stoichiometric screening approximation. Total oxide percentages are not necessarily reactive mineral-phase fractions.

## 7. Illustrative ERW gross and net scenario
`CDR_gross = M_rock × C_theoretical × f_dissolution × f_carbonation`
`CDR_net = CDR_gross - E_LCA`
Ensure the lifecycle emissions term is expressed on the same spatial/temporal basis as gross CDR. This is not an MRV-grade carbon balance.

## 8. Candidate-area screening
The supplied candidate-area statistics report preliminary candidate area and percentage under the supplied thresholds. The area result is a screening output only; it does not establish land access, permissions, ecological acceptability, feedstock suitability or regulatory approval.

## 9. Evidence requirements for verified CDR
Mineralogy and feedstock characterization; treatment and control plots; baseline and repeated soil/water chemistry; alkalinity export and downstream carbon fate; carbonate formation/dissolution; permanence; lifecycle emissions; uncertainty analysis and independent verification.
