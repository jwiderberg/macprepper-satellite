# MacPrepper satellite tiles

Ready-made satellite map tiles for MacPrepper, an offline emergency kit that runs on a Mac. Each release holds one PMTiles file that MacPrepper's map viewer shows as a satellite layer, with no internet needed once it is downloaded.

## What is in a release

- `satellite-recent.pmtiles`: the UAE at about 10 m a pixel, zoom 10 to 14, from one quarter's Sentinel-2 cloud-free mosaic. The release name says which quarter.
- `satellite-recent.json`: the layer's zoom range, label and credit line, read by the map viewer.

The tiles are 256 px JPEGs in web mercator. Any viewer that reads PMTiles can show them, for example MapLibre with the pmtiles plugin.

## Licence and credit

Contains modified Copernicus Sentinel data, from the Sentinel-2 quarterly cloud-free mosaics produced for the European Commission's Copernicus programme. The [Copernicus Sentinel data legal notice](https://sentinels.copernicus.eu/documents/247904/690755/Sentinel_Data_Legal_Notice) allows anyone to copy, share and adapt the data, including for commercial use, as long as the credit stays with it. Keep the line "Contains modified Copernicus Sentinel data [year]" wherever the tiles are shown.

The tiles were made from the original reflectance bands (red, green, blue) with a fixed colour stretch. No other data was added.

## How they are made

MacPrepper's `./macprepper maps satellite --recent` command downloads the mosaic squares from the Copernicus Data Space Ecosystem and cuts them into tiles. The code is in `prepper/satellite.py` and `scripts/satellite_recent.py`in MacPrepper.
