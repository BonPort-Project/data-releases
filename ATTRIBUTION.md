# Attribution — BonPort commune database

The BonPort commune database (licensed under ODbL 1.0, see `LICENSE-DATA`) is built from the
sources below. Any public use of the database, or of anything derived from it, must credit
them. The full per-dataset provenance (producer, licence, vintage, URL, SHA-256 of the file we
used) is in `sources.csv` in the BonPort-Project/data repository. Each `release.json` also
carries it per column, under `sources`.

## Required credit lines

- **« © OpenStreetMap contributors »**: road network (OSRM drive times: A&E, station, coast),
  coastline, cycle paths, nuisances (motorways, airports, wind turbines, power lines, quarries
  and landfills). ODbL 1.0. https://www.openstreetmap.org/copyright
- **SNCF**: station list and national GTFS timetables (TGV, Intercités, TER), used for train
  times and station distances. ODbL 1.0 (share-alike). https://ressources.data.sncf.com
- **Eurostar**: static GTFS timetables (London, Brussels and other international legs).
  Licence Ouverte / Etalab, as recorded in `sources.csv`.
- **Renfe**: AVE / Larga Distancia GTFS (Barcelona leg). « Origen de los datos: Renfe Operadora ».
- **DRIAS**: « DRIAS, données Météo-France, CERFACS, IPSL ». TRACC-2023 climate projections
  (days ≥ 30 °C, horizon 2050), under the DRIAS licence. https://www.drias-climat.fr
- **DGFiP, Demandes de valeurs foncières (DVF)**, 2021–2025, Licence Ouverte / Etalab 2.0.
  Only commune-level medians are published, and only when they rest on at least 5 sales
  (`MIN_SALES_FOR_MEDIAN`). No individual transaction is published, and the data must not be
  used to re-identify sellers or buyers. Alsace-Moselle (57/67/68) is not covered by DVF.

## Licence Ouverte / Etalab 2.0 sources

« Source : <producer>, <dataset>, <vintage> ». Licence Ouverte / Open Licence 2.0:
https://www.etalab.gouv.fr/licence-ouverte-open-licence

| Producer | Dataset(s) |
|---|---|
| INSEE | COG 2026 (communes, mouvements); recensement 2023 (population, logement); BPE 2025; unités urbaines 2020 (édition 2026) |
| IGN | ADMIN EXPRESS COG CARTO 2026 (commune boundaries, chef-lieu points) |
| DGFiP | DVF 2021–2025 (see above); fiscalité locale des particuliers 2025 (TFPB rates) |
| DREES | APL 2024 (médecins généralistes); SAE 2024 (emergency departments) |
| ANS | FINESS+ (structures, activités autorisées) |
| ARCEP | Ma connexion internet (fibre) |
| DHUP (ministère chargé du Logement) | Zonage TLV (zone tendue) |
| MTE / Géorisques (BRGM) | GASPAR (PPR, CatNat) |
| Cerema / MTE | Liste des communes du recul du trait de côte (décret 2026-95) |
| ANCT (Observatoire des territoires) | Périmètres de massifs |

## BonPort's own inputs

- **BonPort, verified A&E sites (Brittany)**: `overrides/ae_sites.csv`. Emergency sites for
  departments 22/29/35/56, checked by hand against sante.fr, ARS Bretagne and hospital
  websites (one `source_url` per site). They correct the FINESS+ GHT grouping. Published as
  part of the database under ODbL 1.0.
