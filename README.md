# Frame — FIX15 Frozen Snapshot

This repository stores the frozen FIX15 snapshot of the time-adaptive aerothermal–thermal–oxidation loosely coupled analysis framework.

## Frozen version

- Version: `FIX15`
- Freeze date: `2026-08-21`
- Validation case: `ADAPT_SIC_NOSE_1000S_PASSIVE`
- Architecture: single Abaqus job, paired `PHYS + 0.01 s AUX` synchronization, no restart
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

## Frozen package

The exact frozen package is stored under `releases/Frame_ADAPT_1000s_SiC_Nose_20260821_FIX15.zip`.

Package SHA256:

`984a28df682ebadac81a615c59008ab359dccc3062d095efe77ea0d96718510a`

The ZIP contains the runtime, Abaqus user-subroutine template, case configuration, trajectory, SiC nose model, preflight assets, documentation, package audit, and SHA256 manifest used for this validated version.

## Local execution

Use the package root scripts:

- `RUN_PREFLIGHT_ONLY.bat`
- `RUN_ADAPT_CASE.bat`
- `COLLECT_RETURN_ONLY.bat`

The validated Windows environment uses Abaqus through `C:\SIMULIA\Commands\abaqus.bat`.

## Freeze policy

`FIX15` is treated as the frozen baseline for subsequent fixed-step/reference comparisons and later development. New method changes should be developed in a new version rather than modifying the frozen FIX15 artifact.
