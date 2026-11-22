<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ANALOG — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Execution inputs.** The maintained checkout and the selected development environment are what the repository controls inspect.

**Received inputs.** Descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**Bounded checks.** Controls inspect bounded local paths and emit fixed diagnostics.

Foundation qualification is in progress.

## Future domain inputs

**Supplied data, with no authority.** The following inputs are treated strictly as supplied data:
- transistor netlists and post-extraction parasitics;
- compiled `OSDI` compact models and corner decks;
- stimulus waveforms and supply-ramp profiles.

They grant no authority to:
- import copyleft Python wrapper libraries in-process;
- claim three-sigma yield from under-sampled Monte Carlo runs;
- export confidential foundry corner waveforms without redaction and release approval;
- issue chip sign-off or publish.

**Comments and embedded text are data.** Descriptions, netlist comments and datasheets arriving inside supplied inputs are data, never instructions to an operator or an agent.

**Public-repository data boundary.** Hosted CI for this public repository runs on public material only. Confidential foundry-NDA, customer, export-controlled or secret-bearing material never enters this repository, its CI or its issues.

## Threats and the rules that answer them

| Threat | Architectural rule |
| --- | --- |
| Optimistic nominal SPICE runs masking ageing, jitter or brown-out lockup | Sign-off studies require aged-silicon degradation corners (`NBTI`, `PBTI`, `HCI`, `TDDB`), power-on and brown-out reset hysteresis above minimum operating supply voltage, derived clock-jitter export and `N >= 2,218` per-corner yield lower bounds |
| Single-simulator timestep or convergence artefacts | Promotion and sign-off rungs cross-check `ngspice` against `Xyce` in separate processes with explicit convergence diagnostics |
| Copyleft licence contamination or confidential PDK waveform leakage | All copyleft simulators and Verilog-A compilers run in separate processes (`PySpice` and `spicelib` forbidden), and post-extraction waveforms from confidential kits stay tagged in their enclave compartment |

## Residuals named, not removed

- **Compact-model extrapolation.** SPICE accuracy outside characterised device geometries and wafer-test ranges rests on the compact-model bounds set by Circuit Devices.

**Not claimed:** no isolation, physical, statistical, safety or durability guarantee is claimed by this foundation.
