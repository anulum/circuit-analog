<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ANALOG — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared local scope.

**What received metadata cannot do:** select another acceptance policy or grant domain authority.

Foundation qualification is in progress.

## Intended domain boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Analogue study | Pinned transistor-level schematic or post-extraction netlist, `OSDI` compact-model digests, supply/temperature/ageing corners, power-on/brown-out ramp profiles and statistical mismatch sample plan | Immutable design-view and technology-profile digests with explicit corner and convergence tolerances |
| Analogue result | Raw operating-point, AC, transient, phase-noise and mismatch waveforms, derived clock-jitter bounds (`J_per`, `J_cc`, duty-cycle distortion) for physical static timing, aged-silicon safe-operating-area margins (`NBTI`, `PBTI`, `HCI`, `TDDB`), dual-simulator `ngspice`-versus-`Xyce` consensus and one-sided yield lower confidence bounds | At least `2,218` independent passing plain Monte Carlo samples at every corner for a zero-failure `95 %` one-sided three-sigma (`99.865 %`) lower bound (using effective sample size under weighted or importance sampling), compartment-tagged waveforms and `glayout` parametrised-cell digests |

## Statistical yield bounds and licence isolation

- **Three-sigma sample-size floor.** With zero observed failures, a claim that at least `99.865 %` of circuits pass (the one-sided three-sigma level, tail `0.00135`) at `95 %` one-sided confidence requires `N >= ln(0.05) / ln(1 - 0.00135) = 2,217.56`, so at least `2,218` independent passing samples (`1 - 0.05^(1/2218) = 0.00135`). With weighted or importance sampling, the bound uses the effective sample size. A claim across several corners holds only if it holds at every corner. Smaller runs report `passed N samples` and their implied `1 - 0.05^(1/N)` bound, never bare `three-sigma`.
- **Separate-process simulators.** Permissive layout generators (`OpenFASOC glayout`, Apache-2.0) may run in-process, while `ngspice`, `Xyce` (`GPL-3.0`), `OpenVAF-Reloaded` (`GPL-3.0`), `VACASK` and proprietary SPICE engines execute strictly as separate processes without importing `GPL-3.0` Python wrappers.

## Planned record schemas

- `circuit_analog.analogue_study.v1`
- `circuit_analog.analogue_result.v1`

These are planned identifiers. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
