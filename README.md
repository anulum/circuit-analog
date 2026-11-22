<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ANALOG — repository foundation
-->

# Circuit Analog

Circuit Analog is being built to specify and execute deterministic transistor-level analogue circuit studies — covering operating points, small-signal and transient response, oscillator and phase-locked-loop jitter bounds, power-on and brown-out reset hysteresis above the minimum operating supply voltage, aged-silicon degradation margins, statistical Monte Carlo mismatch lower confidence bounds and dual-simulator consensus — completely without requiring AI. This checkout contains repository validation tooling and documentation only. Full foundation qualification is in progress. There is no installed SPICE study runner, Monte Carlo mismatch harness, dual-simulator comparator or qualified record schema.

Circuit Analog is part of the **SC Neuromorphic Computing Systems** group (SC-NEUROMORPHIC-COMPUTING-SYSTEMS). The [group and project map](https://github.com/anulum/sc-neurocore/blob/main/docs/ecosystem.md) shows the whole programme and where this repository sits in it.

**What does not exist yet:**
- a SPICE study runner, Monte Carlo harness or dual-simulator comparator;
- a registered runtime record schema;
- a qualified compact-model binary or post-extraction sign-off report.

## Boundary

**What this project owns:**

| Record | Scope |
|---|---|
| Analogue study | Pinned transistor-level schematic or post-extraction netlist, `OSDI` compact-model digests, supply/temperature/ageing corners, power-on/brown-out ramp profiles and statistical mismatch sample plan |
| Analogue result | Raw operating-point, AC, transient, phase-noise and mismatch waveforms, derived clock-jitter bounds (`J_per`, `J_cc`, duty-cycle distortion) for physical static timing, aged-silicon safe-operating-area margins (`NBTI`, `PBTI`, `HCI`, `TDDB`), dual-simulator `ngspice`-versus-`Xyce` consensus and one-sided yield lower confidence bounds |

**Static imports:** only Circuit Core and Circuit Technology.

**Records read without importing domain code:**

| Source | Records consumed |
|---|---|
| Circuit Core | entity references, data-handling profiles, design views, operation profiles, approvals and system budgets |
| Circuit Technology | technology profiles and corner anchors |
| Circuit Devices | approved compact-model candidates and `OSDI` binaries |
| Circuit Fields | electromagnetic and thermal coupling models |
| Circuit Acceptance | acceptance plans and acceptance reports |
| Circuit Flow and Circuit Learning | design-step learning records, circuit graph contracts and grader bundle specifications |

**Capability registration and handoffs:** Registers the analogue tool-profile manifest with Circuit Core and supplies analogue results to Circuit Mixed-Signal, Circuit Physical, Circuit Acceptance and Reliability Witness.

**Explicit non-claims and operating boundaries:**
- Every analogue study and verification rung works deterministically without machine learning.
- It never links copyleft Python wrappers such as `PySpice` or `spicelib` (`GPL-3.0`): `ngspice`, `Xyce`, `OpenVAF-Reloaded` and `VACASK` execute strictly as separate child processes over file boundaries.
- A Monte Carlo pass on fewer than `2,218` independent passing samples (or an effective sample size below `2,218` under weighted or importance sampling) at every corner is never reported as a `95 %` one-sided three-sigma (`99.865 %`) yield claim; smaller sample counts report `passed N samples` with their exact implied lower confidence bound.

## Current tooling

Repository controls inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and repository inventory;
- preflight orchestration.

Metadata declares architecture-only maturity with empty implemented domain capability and claim inventories.

- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the maintained validation scope.

## Intended evidence

Every future domain artefact will carry the platform's common provenance envelope, its source and environment digests, its confidentiality compartment and its explicit verification boundary. None of the planned record schemas is registered or qualified by this foundation.

## Documentation and support

Read [Architecture](ARCHITECTURE.md), [support](SUPPORT.md), [security reporting](SECURITY.md) and [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a performed simulation, hardware measurement or sign-off verdict.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
