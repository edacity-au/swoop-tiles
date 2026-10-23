# Swoop routing tiles

Prebuilt [Valhalla](https://github.com/valhalla/valhalla) routing tiles for the Swoop app's
service areas, all of Australia since 2026-10-23, published as release assets so the routing
service can download them without credentials. Nothing else lives here: the code that builds
them is in Swoop's private repository.

Each release holds:

- `tiles.parts.json`: the bundle's manifest, listing its parts in order with each one's size
  and SHA-256, and the whole bundle's.
- `tiles.tar.000` (and `tiles.tar.001` on, when there are more): the bundle, one tar cut into
  parts under GitHub's 2 GiB asset limit. Joined in order they are `tiles.tar`: the Valhalla
  3.9.0 tiles, the admin and time-zone databases, `lit_ways.csv.gz` and `BUILD_INFO`.
- `tiles.tar.sha256`: the joined tar's SHA-256.
- `lit_ways.csv.gz`: the ids of the OpenStreetMap ways counted as lit (tagged `lit=yes`, or
  within 25 m of a mapped street lamp).
- `lit_geometry.ndjson.gz`: those ways' geometry, merged into chains and simplified to 2 m.
- `lamps.csv.gz`: every mapped street lamp (`highway=street_lamp`) as longitude, latitude.
- `BUILD_INFO`: what was built from what.

Releases before 2026-10-23 hold one `tiles.tar` in place of the parts and the manifest, and
`tiles-2026-10-09-1` and older have no `lit_geometry.ndjson.gz` or `lamps.csv.gz`.

## Data and licence

Every file above is derived from **OpenStreetMap** data, © OpenStreetMap contributors,
available under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/):
the tiles and the bundle's parts, `lit_ways.csv.gz`, `lit_geometry.ndjson.gz` and
`lamps.csv.gz` are each a derivative database, released under the same licence. Elevation
data in the tiles is from the SRTM/Copernicus public datasets as bundled by Valhalla's tooling.
