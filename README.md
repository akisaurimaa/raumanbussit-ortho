# Rauman ortokuvatiilet

Itse isännöidyt XYZ-tiilet (`{z}/{x}/{y}.jpg`, zoomit 13-17) Rauman alueelta [Rauman bussit](https://raumanbussit.azurewebsites.net) -sovelluksen 3D-näkymän ja kartan ilmakuvaa varten. Tiilet on tehty Maanmittauslaitoksen tiedostopalvelun 0,5 m ortokuvasta (JPEG2000), koska avoin WMTS-ortokuva on ylipakattua ja sumeaa.

Lähde: Maanmittauslaitos, Ortokuva, 2025, ladattu 2026-09-30, CC BY 4.0.

Alue: leveys 61.05-61.2, pituus 21.35-21.7 (WGS84). Tiiliä 19536, yhteensä 383 Mt.

## Uudelleenluonti

Rauman bussit -repossa:

```
python3 scripts/build_ortho_tiles.py
```

Tarvitsee GDAL:n (`gdalbuildvrt`, `gdal2tiles.py`, JP2OpenJPEG) ja Pillowin sekä ympäristömuuttujan `MML_API_KEY`. Tulos kirjoitetaan tähän repoon ja `meta.json` päivittyy.
