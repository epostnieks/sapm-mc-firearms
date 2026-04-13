# Data Sources — Firearms Monte Carlo Simulation

Channel parameters in `mc_simulation.py` trace to the sources listed here.
The paper (Firearms: Constitutional Ratchet) is available on SSRN and contains the full
reference list and §4 calibration narrative.

---

## Channel Sources

### `C1_vsl_mortality`

VSL-adjusted gun deaths (48K US + global scaling)

*Full citations: paper §4 (available SSRN).*

### `C2_healthcare_morbidity`

Gunshot wound treatment, rehabilitation, disability

*Full citations: paper §4 (available SSRN).*

### `C3_criminal_justice`

Incarceration, prosecution, policing costs

*Full citations: paper §4 (available SSRN).*

### `C4_lost_productivity`

Lost earnings from premature death and disability

*Full citations: paper §4 (available SSRN).*

### `C5_community_damage`

Community psychological damage, property, insurance

*Full citations: paper §4 (available SSRN).*

### `C6_governance`

PLCAA regulatory capture, NRA lobbying distortion

*Full citations: paper §4 (available SSRN).*

---

## Industry Revenue (Π)

The private payoff Π = $10.0B/yr is global annual industry revenue.
Source: paper §2 and §4. See paper §DA-1 (Decision Audit Field 7) for full
revenue source documentation.

---

## SAPM Framework

- Postnieks, E. (2026). *The Private Pareto Theorem*. SAPM Foundation Paper. SSRN.
- Postnieks, E. (2026). *Firearms (Constitutional Ratchet)*. SAPM Working Paper. SSRN.

---

## Distribution Methodology

- Iman, R. L., & Conover, W. J. (1982). A distribution-free approach to
  inducing rank correlation among input variables. *Communications in
  Statistics — Simulation and Computation*, 11(3), 311–334.
- Cooke, R. M. (1991). *Experts in Uncertainty*. Oxford University Press.
