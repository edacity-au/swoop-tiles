# Swoop routing tiles

Prebuilt [Valhalla](https://github.com/valhalla/valhalla) routing tiles for the Swoop app's
service areas, published as release assets so the routing service can download them without
credentials. Nothing else lives here: the code that builds them is in Swoop's private
repository.

Each release holds `tiles.tar` (Valhalla 3.9.0 tiles, admins and time-zone databases, the
lit way-id set and `BUILD_INFO`) and its SHA-256.

## Data and licence

The tiles are derived from **OpenStreetMap** data, © OpenStreetMap contributors, available
under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/).
As a derivative database they are released under the same licence. Elevation data, where
included, is from the SRTM/Copernicus public datasets as bundled by Valhalla's tooling.
