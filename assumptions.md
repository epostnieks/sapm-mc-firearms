# Monte Carlo Assumptions — Firearms / Constitutional Ratchet

All values in $B USD (annualized). Every parameter traces to paper §4–§5
or the citations in `data_sources.md`. Run `python mc_simulation.py` to
reproduce bit-identical results.

---

## Simulation Parameters

| Parameter | Value | Justification |
|-----------|-------|---------------|
| Seed | 42 | Fixed for reproducibility |
| N draws | 100,000 | 4-decimal CI stability |
| Cross-channel correlation ρ | 0.3 | Shared macro drivers (GDP, population, regulation) |
| Private payoff Π | $10.0B/yr | Annual industry revenue — see `data_sources.md` |
| β_W median (result) | 50.99 | Confirmed by N=100,000 draws |
| ΔW median (result) | $509.9B/yr | Sum of channel medians (correlated) |

**Π = revenue, not profit.** SAPM Iron Law: βW = ΔW/Π where Π is annual
revenue. Using profit would inflate βW by 5–20× for low-margin industries.

---

## Channel Parameters

| Channel | Dist | Low | Mid | High | Description |
|---------|------|-----|-----|------|-------------|
| `C1_vsl_mortality` | lognormal | $330B | $434B | $560B | VSL-adjusted gun deaths (48K US + global scaling) |
| `C2_healthcare_morbidity` | normal | $7.0B | $8.7B | $11.0B | Gunshot wound treatment, rehabilitation, disability |
| `C3_criminal_justice` | normal | $7.0B | $8.8B | $11.0B | Incarceration, prosecution, policing costs |
| `C4_lost_productivity` | lognormal | $35B | $45.7B | $60B | Lost earnings from premature death and disability |
| `C5_community_damage` | lognormal | $8.0B | $11.3B | $16B | Community psychological damage, property, insurance |
| `C6_governance` | lognormal | $0.5B | $0.75B | $1.2B | PLCAA regulatory capture, NRA lobbying distortion |


All ranges represent [P5, P95] of the channel-specific distribution as
calibrated from literature in paper §4.

---

## Impossibility Floor

The floor β_W ≥ 1.0 is the minimum ratio achievable while the industry operates.
This bounds the simulation from below: the theorem holds regardless of parameter values,
because even best-case scenarios exceed the floor.

In 100,000 draws: P(β_W < 1.0) = 0.0000%

## Sensitivity (VSL × Double-Counting Grid)

Central VSL (1.0×): no DC adj β_W = 50.92 | 20% DC adj = 40.74 | 40% DC adj = 30.55

See `mc_results.json` → `sensitivity_matrix` for full 5×5 grid.

## Distribution Robustness

The simulation uses a lognormal/normal mix calibrated to channel-specific
uncertainty structure. Results are robust: the central β_W changes by less
than ±0.3 under all-lognormal or all-normal configurations.

---

## Plausibility Checks (SAPM IL#28)

- **Annual flow**: All W_i are $/yr flows ✓
- **GDP bound**: ΔW = $510B = 0.5% of world GDP ($106T) ✓
- **β_W range**: 50.99 is within the [0.5, 100] plausible range ✓
- **P(β_W < 1)**: 0.0000% ✓
