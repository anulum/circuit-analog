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

Circuit Analog is being built to specify and execute deterministic transistor-level analogue circuit studies — covering operating points, small-signal and transient response, oscillator and phase-locked-loop jitter bounds, power-on and brown-out reset hysteresis above the minimum operating supply voltage, aged-silicon degradation margins, statistical Monte Carlo mismatch lower confidence bounds and dual-simulator consensus — completely without requiring AI. Its current executable surface is repository validation tooling. It has no installed SPICE study runner, Monte Carlo mismatch harness, dual-simulator comparator or qualified record schema.

Read [Architecture](ARCHITECTURE.md), [validation tooling](validation-tooling.md), [data boundaries](THREAT_MODEL.md) and the [repository boundary decision](adr/0001-repository-boundary.md).
