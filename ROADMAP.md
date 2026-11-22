<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ANALOG — repository foundation
-->

# Roadmap

## Current foundation

**Being qualified:**
- repository identity and legal texts;
- architecture and governance;
- native documentation;
- dedicated validation tools.

**Domain capabilities and claims:** empty.

## Capability milestones

1. **The two planned v1 record schemas with golden fixtures** (`analogue_study`, `analogue_result`), enrolled with full quality gates.
2. **Separate-process `ngspice` and `Xyce` runner adapters** with `OpenVAF-Reloaded` `OSDI` digest verification on open PDKs.
3. **Oscillator/PLL jitter extraction, brown-out hysteresis and aged-silicon safe-operating-area checks.**
4. **Per-corner Monte Carlo mismatch evaluator** enforcing sample-size and one-sided confidence-bound reporting.

**Enrolled with every implementation change:**
- strict native typing and linting;
- native documentation;
- meaningful statement and branch coverage;
- affected boundary tests and benchmarks.

**Requires its own evidence and explicit approval:**
- admitting any proprietary SPICE engine;
- downward summary release from confidential PDK runs;
- public activation and release.

No availability date is promised. No performance, yield or productivity gain is promised either.
