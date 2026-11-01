# Rauman ortokuvatiilet

Itse isännöidyt XYZ-tiilet (`{z}/{x}/{y}.jpg`, zoomit 11-17) Rauman alueelta [Rauman bussit](https://raumanbussit.azurewebsites.net) -sovelluksen 3D-näkymän ja kartan ilmakuvaa varten. Tiilet on tehty Maanmittauslaitoksen tiedostopalvelun 0,5 m ortokuvasta (JPEG2000), koska avoin WMTS-ortokuva on ylipakattua ja sumeaa.

Lähde: Maanmittauslaitos, Ortokuva, 2025, ladattu 2026-11-01, CC BY 4.0.

Alue: leveys 61.037012232401885-61.22795717667786, pituus 21.26953125-21.708984375 (WGS84). Tiiliä 38908, yhteensä 714 Mt.

## Uudelleenluonti

Rauman bussit -repossa:

```
python3 scripts/build_ortho_tiles.py
```

Tarvitsee GDAL:n (`gdalbuildvrt`, `gdal2tiles.py`, JP2OpenJPEG) ja Pillowin sekä ympäristömuuttujan `MML_API_KEY`. Tulos kirjoitetaan tähän repoon ja `meta.json` päivittyy.

Laajennus: lisäksi 24 z13-tiiltä (ja niiden z14-17-jälkeläiset) bussireittien varrelta perusalueen ulkopuolelta, 600 m puskurilla (`extra_z13` ja `union_bbox` meta.jsonissa; `python3 scripts/build_ortho_tiles.py --extend-routes 600`).
