<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ANALOG — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No domain component of Circuit Analog is implemented yet. The metadata keeps domain capabilities, claims and qualified record formats empty.

## Intended data flow

1. **Study setup** binds a pinned design view, system budget, technology corner set, approved `OSDI` compact models and electromagnetic/thermal couplings.
2. **Dual-simulator execution** runs `ngspice` and `Xyce` in separate processes across nominal, supply/temperature, brown-out hysteresis and aged-silicon corners.
3. **Statistical mismatch grading** evaluates per-corner Monte Carlo ensembles and computes one-sided confidence lower bounds on yield.
4. **Downstream export** delivers derived oscillator/PLL jitter bounds directly into post-layout timing constraints and tags confidential corner waveforms with their source compartment.

## Ownership

**This project owns** the planned Circuit Analog records and boundary rules.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| contracts, compartments and approvals | Circuit Core |
| process technology corners | Circuit Technology |
| TCAD and compact-model extraction | Circuit Devices |
| 3D electromagnetic and thermal solvers | Circuit Fields |
| coupled mixed-signal verification | Circuit Mixed-Signal |
| layout, parasitic extraction and static timing | Circuit Physical |
| sign-off verdicts | Circuit Acceptance |

## Interpretation

- **Pre-layout netlists.** Schematic SPICE results do not include layout parasitics.
- **Sample counts.** Fewer than `2,218` zero-failure samples cannot support a `95 %` one-sided three-sigma yield statement.

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records, domain rules and schema identifiers.
