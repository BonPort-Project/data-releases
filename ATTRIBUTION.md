# Attribution — BonPort commune database

The BonPort commune database (licensed under ODbL 1.0, see `LICENSE-DATA`) is built from the
sources below. Any public use of the database, or of anything derived from it, must credit
them. The per-column provenance (producer, licence, vintage, URL) is in each release's
`release.json`, under `sources`.

## Required credit lines

- **« © OpenStreetMap contributors »**: road network (OSRM drive times: A&E, station, coast,
  nearest big city),
  coastline, cycle paths, nuisances (motorways, airports, wind turbines, power lines, quarries
  and landfills). ODbL 1.0. https://www.openstreetmap.org/copyright
- **SNCF**: station list and national GTFS timetables (TGV, Intercités, TER), used for train
  times and station distances. ODbL 1.0 (share-alike). https://ressources.data.sncf.com
- **Eurostar**: static GTFS timetables (London, Brussels and other international legs).
  Licence Ouverte 2.0. https://www.etalab.gouv.fr/licence-ouverte-open-licence
- **Renfe**: AVE / Larga Distancia GTFS (Barcelona leg). « Origen de los datos: Renfe Operadora ».
  CC BY 4.0. https://creativecommons.org/licenses/by/4.0/
- **DRIAS**: « DRIAS, données Météo-France, CERFACS, IPSL ». TRACC-2023 climate projections
  (days ≥ 30 °C, horizon 2050). Licence Ouverte / Etalab 2.0. https://www.drias-climat.fr
- **DGFiP, Demandes de valeurs foncières (DVF)**, July 2021 – June 2026 (Etalab geolocated files, October 2026 delivery), Licence Ouverte / Etalab 2.0.
  Only commune-level medians are published, and only when they rest on at least 5 sales
  (`MIN_SALES_FOR_MEDIAN`). No individual transaction is published, and the data must not be
  used to re-identify sellers or buyers. Alsace-Moselle (57/67/68) is not covered by DVF.

## Licence Ouverte / Etalab 2.0 sources

« Source : <producer>, <dataset>, <vintage> ». Licence Ouverte / Open Licence 2.0:
https://www.etalab.gouv.fr/licence-ouverte-open-licence

| Producer | Dataset(s) |
|---|---|
| INSEE | COG 2026 (communes, mouvements); recensement 2023 (population, logement); BPE 2025 (counts and detailed geolocated file); unités urbaines 2020 (édition 2026); zones d'emploi 2020 (communes au 01/01/2026); taux de chômage localisés par zone d'emploi, 2025; Insee Première n° 2073, figure 2 (mobilités résidentielles par région, 2013–2023) |
| IGN | ADMIN EXPRESS COG CARTO 2026 (commune boundaries, chef-lieu points); OCS GE, 2021–2023 vintage (land cover) |
| DGFiP | DVF July 2021 – June 2026 (see above); fiscalité locale des particuliers 2025 (TFPB rates); REI 2025 (TFPB bases, rates and amounts: bill per dwelling) |
| DREES | APL 2024 (médecins généralistes); SAE 2024 (emergency departments) |
| ANS | FINESS+ (structures, activités autorisées) |
| ARCEP | Ma connexion internet (fibre) |
| DHUP (ministère chargé du Logement) | Zonage TLV (zone tendue) |
| Île-de-France Mobilités | Horaires prévus sur les lignes de transport en commun d'Île-de-France (GTFS Datahub): RER and Transilien timetables of 18/11/2026 in the train times — **Licence Mobilités**, see below |
| MTE / Géorisques (BRGM) | GASPAR (PPR, CatNat) |
| Cerema / MTE | Liste des communes du recul du trait de côte (décret 2026-95) |
| ANCT (Observatoire des territoires) | Périmètres de massifs |
| Ministère de la Culture | Base Mérimée, immeubles protégés au titre des monuments historiques (POP open data, Licence Ouverte / Etalab 2.0) |
| Urssaf | Effectifs salariés du secteur privé par zone d'emploi, trimestriels (CVS), T2 2023 – T2 2026 — **ODbL** (open.urssaf.fr), not Licence Ouverte |
| SSMSI (Ministère de l'Intérieur) | Base statistique communale de la délinquance enregistrée par la police et la gendarmerie nationales, 2023–2025 (cambriolages de logement) |

## BonPort's own inputs

- **BonPort, verified A&E sites (Brittany)**: emergency sites for
  departments 22/29/35/56, checked by hand against sante.fr, ARS Bretagne and hospital
  websites (one `source_url` per site). They correct the FINESS+ GHT grouping. Published as
  part of the database under ODbL 1.0.

## Île-de-France Mobilités timetables (Licence Mobilités)

Contient des informations de [Horaires prévus sur les lignes de transport en commun d'Île-de-France (GTFS Datahub)](https://data.iledefrance-mobilites.fr/explore/dataset/offre-horaires-tc-gtfs-idfm/),
présentement mises à disposition aux conditions de la [« Licence Mobilités »](https://cloud.fabmob.io/s/eYWWJBdM3fQiFNm).

Timetables of the reference day, Wednesday 18 November 2026 (file downloaded on 4 November 2026). The train times
are computed per commune from them; the timetables themselves are not republished.

