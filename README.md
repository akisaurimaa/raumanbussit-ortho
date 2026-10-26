# Rauman ortokuvatiilet

Itse isännöidyt XYZ-tiilet (`{z}/{x}/{y}.jpg`, zoomit 11-17) Rauman alueelta [Rauman bussit](https://raumanbussit.azurewebsites.net) -sovelluksen 3D-näkymän ja kartan ilmakuvaa varten. Tiilet on tehty Maanmittauslaitoksen tiedostopalvelun 0,5 m ortokuvasta (JPEG2000), koska avoin WMTS-ortokuva on ylipakattua ja sumeaa.

Lähde: Maanmittauslaitos, Ortokuva, 2025, ladattu 2026-10-26, CC BY 4.0.

Alue: leveys 61.037012232401885-61.22795717667786, pituus 21.26953125-21.708984375 (WGS84). Tiiliä 30724, yhteensä 538 Mt.

Zoomit 13-17 ovat pelkkää MML:n ortokuvaa. Zoomit 11-12 (34 tiiltä) on tehty z13-tiilistä, ja niiden puuttuvat reunat on täytetty muokkaamattomalla EOX Sentinel-2 cloudless -kuvalla (`scripts/build_ortho_overviews.py`), jotta kaukaa katsottaessa ortokuvan ja Sentinelin raja ei näy.

## Uudelleenluonti

Rauman bussit -repossa:

```
python3 scripts/build_ortho_tiles.py
```

Tarvitsee GDAL:n (`gdalbuildvrt`, `gdal2tiles.py`, JP2OpenJPEG) ja Pillowin sekä ympäristömuuttujan `MML_API_KEY`. Tulos kirjoitetaan tähän repoon ja `meta.json` päivittyy.
