# Frame — FIX15 Frozen Baseline

This repository stores the frozen FIX15 baseline of the time-adaptive aerothermal–thermal–oxidation loosely coupled analysis framework.

## Frozen version

- Version: `FIX15`
- Freeze date: `2026-08-21`
- Validation case: `ADAPT_SIC_NOSE_1000S_PASSIVE`
- Architecture: one Abaqus job, paired `PHYS + 0.01 s AUX` synchronization, no restart
- Outer advancement: trajectory-aware adaptive coupling
- Inner advancement: inherited accepted increment + temperature-change rate + external aerothermal-load variation
- Net heat-flux history: unified DFLUX accepted-end record for both PHYS and AUX

## Validated 1000 s result

- PHYS accepted increments: 75
- AUX accepted increments: 22
- Rejected trial attempts: 27
- Peak accepted-end temperature: 1890.653 K
- Peak unified net heat flux: 2.4917 MW/m²
- Final synchronized recession: 0.425608 μm
- Maximum PHYS/AUX net-heat-flux boundary mismatch: 0.1218%
- Median PHYS/AUX net-heat-flux boundary mismatch: 0.0148%
- Active recession / geometry refresh: none in this passive validation case

## Frozen artifacts

- Browsable freeze record: `FREEZE_FIX15.md`
- Source snapshot archive: `releases/FIX15_source_only.tar.gz`
- Exact validated local package name: `Frame_ADAPT_1000s_SiC_Nose_20260821_FIX15.zip`
- Exact validated package SHA256: `984a28df682ebadac81a615c59008ab359dccc3062d095efe77ea0d96718510a`

The source snapshot contains the runtime source, Abaqus user-subroutine template, configuration, model, trajectory, tools, tests and documentation used by FIX15. The exact full runnable ZIP is retained as the validated release artifact identified by the SHA256 above; it also contains large generated/preflight/database assets that are intentionally not duplicated into the Git source tree.

## Local execution

Use the package root scripts:

- `RUN_PREFLIGHT_ONLY.bat`
- `RUN_ADAPT_CASE.bat`
- `COLLECT_RETURN_ONLY.bat`

Validated Windows Abaqus command: `C:\SIMULIA\Commands\abaqus.bat`.

## Freeze policy

`FIX15` is the frozen baseline for fixed-step/reference comparisons and later method development. New changes should use a new version/branch rather than modifying this frozen baseline.
