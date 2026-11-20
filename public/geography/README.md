# Geografia pubblica - edizione Calabria

La cartografia pubblica dell'edizione Calabria comprende:

- `atlas_region.geojson`: confine regionale ISTAT 2026 (codice 18);
- `atlas_provinces.geojson`: 5 unità sovracomunali ISTAT 2026: Cosenza (078), Catanzaro (079), Città metropolitana di Reggio Calabria (280), Crotone (101), Vibo Valentia (102);
- `atlas_municipalities.geojson`: 404 comuni ISTAT al 1/1/2026.

Fonte: ISTAT, «Confini delle unità amministrative a fini statistici al 1° gennaio 2026», versione generalizzata (Limiti01012026_g.zip, SHA-256 in `metadata/SNAPSHOTS.tsv`), CC BY 4.0. Gli attributi dei DBF sono letti in UTF-8 e le coordinate sono convertite da EPSG:32632 a WGS84 da `scripts/build_istat_geography.py`.

Gli studi della letteratura curata stanno in layer distinti sotto `public/data/`. Nessuna struttura è un punto: l'unico presidio nominato (AOU R. Dulbecco, presidio Mater Domini, Catanzaro; 2 studi) non ha un oggetto ospedaliero su OSM Nominatim (16 richieste, 2026-11-20; risposte grezze in `raw/nominatim/`), quindi i due studi stanno sul comune di Catanzaro. Gli ospedali non nominati restano su comune, provincia o regione.
