<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ANALOG — repository foundation
-->

# Validation

This checkout's repository foundation is under qualification. Another repository's tests or coverage do not qualify it.

**Not qualified here:**
- any analogue-study or analogue-result schema;
- SPICE execution, dual-simulator comparison or Monte Carlo yield calculation;
- any circuit block or compact model.

## Maintained scope

The Python repository controls and their dedicated tests are enrolled in:
- Ruff linting and formatting;
- strict mypy;
- native NumPy-style documentation;
- statement and branch coverage.

**Coverage target:** full meaningful coverage of every maintained source file.

**Test surface:** each repository control exposes a public entry point tested on both success and refusal paths.

## Local and CI entry points

- **Environment:** the selected interpreter and hash-locked dependencies in [Contributing](CONTRIBUTING.md).
- **Named make targets:** inspect their declared local scopes only.
- **Full runs:** full `make ci` and `make preflight` belong in CI or in an admitted pre-push environment.
- **Partial preflight:** records omitted checks as not run and never clears whole-repository acceptance.
- **Public CI:** runs on public material only.

## Evidence limits

- **Pre-layout netlists.** Schematic SPICE results do not include layout parasitics.
- **Sample counts.** Fewer than `2,218` independent passing samples (or an effective sample size below `2,218` under importance weighting) at every corner cannot support a `95 %` one-sided three-sigma (`99.865 %`) yield statement.
- **Workflows.** A static workflow policy check is not hosted execution.

**The maintained repository controls do not establish:**
- domain correctness or physical sign-off;
- a release or DOI;
- hosted acceptance.
