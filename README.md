# BonPort data releases

[BonPort](https://bonport.app) helps you choose where to live in France. You answer a short
questionnaire, and it ranks France's 34,746 communes on what matters to you.

This repository holds **published data releases only**: the commune database behind BonPort,
as versioned [GitHub releases](../../releases). It contains no code.

## What a release contains

| File | Content |
|---|---|
| `communes_fr.csv`, `communes_fr.parquet` | The full commune table (mainland France + Corsica, COG 2026), one row per commune |
| `communes_fr.pmtiles` | Commune boundaries as vector tiles |
| `base.json`, `train-<origin>.json`, `tags.json` | The same data, split into the files the website loads |
| `scoring-config.json` | The scoring model the release was built against |
| `release.json` | Manifest: version, row count, file list, SHA-256 checksums, per-column sources |
| `changes.json` | What changed in this release |
| `LICENSE-DATA`, `ATTRIBUTION.md` | Licence and required credits |

Release tags are immutable. A correction ships as a new version and never replaces an existing one.

## Licence

The commune database (`communes_fr.*`, `base.json`, `train-*.json`, `tags.json`) is licensed under
the **Open Database License (ODbL) 1.0**; see [`LICENSE-DATA`](LICENSE-DATA). It is derived in
part from OpenStreetMap and SNCF data, both ODbL, so any public use of the database or of a
derivative database must remain under the ODbL and credit the sources listed in
[`ATTRIBUTION.md`](ATTRIBUTION.md), starting with « © OpenStreetMap contributors ».

`scoring-config.json`, `release.json` and `changes.json` are not part of the database and are
not covered by the ODbL.

Property prices come from DGFiP's DVF (Demandes de valeurs foncières). Only commune-level
medians are published, and only when they rest on at least 5 sales.

## Verifying a download

`release.json` lists a SHA-256 checksum for every other file in the release:

```sh
gh release download data-v0.4.8 -R BonPort-Project/data-releases -D bonport-data-v0.4.8
cd bonport-data-v0.4.8
jq -r '.checksums | to_entries[] | "\(.value)  \(.key)"' release.json | shasum -a 256 -c -
```

Every line should end in `OK`. On Linux, use `sha256sum -c -` instead of `shasum -a 256 -c -`.
The same checksums are also printed in each release's notes.
