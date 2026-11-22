<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ANALOG — repository foundation
-->

# Decision: isolate transistor-level SPICE, ageing and statistical mismatch verification in Circuit Analog

## Context

Analogue blocks fail in silicon from supply brown-out hysteresis gaps, oscillator jitter, hot-carrier or bias-temperature ageing and single-simulator convergence quirks long before digital logic fails, while popular Python SPICE wrappers carry copyleft licences.

## Decision

**What Circuit Analog owns:**
- analogue study;
- analogue result;

**What it imports:** only Circuit Core and Circuit Technology.

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

## Consequences

**What can be qualified now:** repository governance and validation tooling, before domain code exists.

**What it cannot qualify:** unimplemented schemas, solvers, hardware or sign-off verdicts.

**Architectural consequences:**
- Circuit Analog owns transistor-level studies and results, dual-simulator consensus, ageing margins and `N >= 2,218` statistical yield bounds;
- simulators and Verilog-A compilers execute strictly in separate processes with zero copyleft library linkage;
- device physics extraction stays in Circuit Devices and coupled digital/analogue co-simulation stays in Circuit Mixed-Signal.
