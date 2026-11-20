# Calabria One Health AMR Atlas

Edizione regionale `calabria_amr_atlas`, pubblicata da Codex Vitae ETS sulla stessa
base dell'edizione Campania.

## Stato

La letteratura pubblicata con collegamento territoriale esplicito alla Calabria
è concentrata su Catanzaro (AOU R. Dulbecco e Università Magna Graecia) e sulla
regione intera. Ne restano 19 inclusi (20 novembre 2026): nessuno di struttura
georiferita, 6 di comune, 3 di provincia e 10 a scala regionale.

Nessuna struttura è un punto. Il presidio Mater Domini dell'AOU R. Dulbecco
(2 studi) non ha un oggetto ospedaliero su OSM Nominatim (16 richieste,
20 novembre 2026, © OpenStreetMap contributors, ODbL) e sta sul comune di
Catanzaro. «Renato Dulbecco University Hospital» senza presidio resta sullo
stesso comune: l'AOU ha due presidi, Mater Domini e Pugliese-Ciaccio.
L'ospedale universitario di terzo livello della provincia di Catanzaro resta
sulla provincia.

Catanzaro ha 6 studi. Uno studio copre i comuni di Catanzaro e Cosenza.
Cosenza ha 1 studio (provincia, salumi e formaggi). Reggio Calabria ha 1 studio
(Parco dell'Aspromonte, Città metropolitana). Crotone e Vibo Valentia non hanno
studi con luogo provinciale esplicito. Dieci studi a scala regionale usano il
contorno della regione: 6 umani sul layer di contorno e 4 veterinari sul layer
veterinario.

Per settore: 11 AMR clinica, 2 stewardship, 4 veterinaria (MRSA/LA-MRSA su
allevamenti suini e ovini), 1 fauna selvatica, 1 alimentare, 0 ambientale.

L'IZS del Mezzogiorno copre Campania e Calabria: sono inclusi solo gli studi
che separano i dati calabresi.

L'edizione pubblica AR-ISS 2024 (copertura 42,7%, 4 laboratori referenti,
numerosità 63-302 isolati, CC BY 4.0; attribuzione Istituto Superiore di
Sanità) e AIFA Open Data 2024, antibatterici J01 (CC BY 4.0; codreg 180;
convenzionata 3.117.041 confezioni e 24,79 milioni di euro, acquisti diretti
576.822 confezioni e 8,88 milioni di euro; attribuzione Agenzia Italiana del
Farmaco). Il report regionale ICA/MDR 2022-2023 è escluso per licenza.

Sei layer (AMR umana, veterinaria, alimentare, ambientale, fauna selvatica,
contorno regionale):

- AMR umana: 3 elementi, 7 studi (comune di Catanzaro; comuni di Catanzaro e Cosenza; provincia di Catanzaro);
- AMR veterinaria: 1 elemento (regione), 4 studi;
- AMR alimentare: 1 elemento (provincia di Cosenza), 1 studio;
- AMR ambientale: vuoto (0 elementi);
- AMR nella fauna selvatica: 1 elemento (Città metropolitana di Reggio Calabria), 1 studio;
- studi a scala regionale: 1 elemento, 6 studi umani sul contorno.

I layer vuoti e le aree senza segnaposto sono nessuna evidenza pubblicata,
non resistenza zero. Ogni popup cita lo studio e il DOI (o il record PubMed
se il DOI non è assegnato) e ricorda che il segnaposto è il luogo dello
studio, non una prevalenza.

Confini ISTAT 2026 (404 comuni, 5 unità sovracomunali, regione 18), letti in
UTF-8. Il report ICA/MDR, dati.regione.calabria.it, le ASP, le aziende
ospedaliere, ARPACAL, il catalogo open data dell'IZSM e il PDF OsMed sono
esclusi: vedi `metadata/EXCLUDED_SOURCES.md`.

Il conteggio in homepage e in pubblicazioni legge
`public/data/literature-catalog.json` (19).

## Pagine

Sorgente su `main`. Il sito statico è pubblicato dal branch `gh-pages`
(GitHub Pages, cartella `/`). Nessun file `CNAME`. Analitica: GoatCounter
`https://atlanteamr.goatcounter.com/count`, come le edizioni Lazio, Molise e
Campania.

## Build locale

```bash
python3 -m http.server 8000
```

Aprire `http://localhost:8000/`.

Per rigenerare i dati pubblici servono gli input in `raw/` e, per i confini,
l'archivio ISTAT indicato in `metadata/SNAPSHOTS.tsv`. I DBF ISTAT si leggono
in UTF-8:

```bash
pip install -r requirements-geodata.txt
python3 scripts/build_istat_geography.py --source-root <Limiti01012026_g> --output-root public/geography
python3 scripts/build_literature_catalog.py
python3 scripts/build_study_evidence_layers.py
```

## Directory

- `public/`: dati e asset approvati per il sito;
- `metadata/`: fonti, snapshot, ambito pubblico e fonti escluse;
- `raw/`: curatela, esummary e risposte Nominatim;
- `scripts/`: ricostruzione del catalogo e dei layer;
- `private/`: nessun dato riservato in questa edizione.
