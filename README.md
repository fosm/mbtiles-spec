# MBTiles Specification

MBTiles is a specification for storing arbitrary tiled map data in
[SQLite](http://sqlite.org/) databases for immediate usage and for transfer.
MBTiles files, known as **tilesets**, must implement the specification below
to ensure compatibility with devices.

## UTFGrid

The MBTiles specification previously contained the
[UTFGrid specification](https://github.com/mapbox/utfgrid-spec).
It was removed in version 1.2 and moved into its own specification
with synced version numbers - so MBTiles 1.2 is compatible with
UTFGrid 1.2. The specs integrate but do not require each other
for compliance.

# Versions

* **Development** - NOT USABLE: [1.2](https://github.com/mapbox/mbtiles-spec/blob/master/1.2/spec.md)
* **Stable**: [1.1](https://github.com/mapbox/mbtiles-spec/blob/master/1.1/spec.md)
* [1.0](https://github.com/mapbox/mbtiles-spec/blob/master/1.0/spec.md)

# Changelog

## Roadmap

* The format will switch tile ordering to the XYZ schema popularized by
  OpenStreetMap and away from the Tile Map Service specification.

## 2.0

* Allow data other than PNG and JPEG images to be stored in tilesets
* Use MIME type for `format` metadata.
* Added RECOMMENDED `compression` metadata.

## 1.1

* Made `format` metadata REQUIRED.
* Added OPTIONAL `bounds` metadata.
* optional UTFGrid-based interaction spec.

# Concept

MBTiles is a compact, restrictive specification. It supports only
tiled data, including image tiles and interactivity grid tiles. Only the
Spherical Mercator projection is supported for presentation - tile display -
and only latitude-longitude coordinates are supported for metadata such
as bounds and centers.

It is a minimum specification - only specifying the ways in which data
must be retrievable. Thus MBTiles files can internally compress and optimize
data, and construct views that adhere to the MBTiles specification.

Unlike [Spatialite](http://www.gaia-gis.it/spatialite/), GeoJSON,
and Rasterlite, MBTiles is not raw data storage - it is storage
for presentational data, like rendered map tiles.

One MBTiles file represents a single tileset, optionally including grids
of interactivity data. Multiple tilesets - layers, or maps in other terms,
can be represented by multiple MBTiles files.

# [Implementations](https://github.com/mapbox/mbtiles-spec/wiki/Implementations).

# License

The text of this specification is licensed under a
[Creative Commons Attribution 3.0 United States License](http://creativecommons.org/licenses/by/3.0/us/).
However, the use of this spec in products and code is entirely free:
there are no royalties, restrictions, or requirements.

# Authors

* Tom MacWright (tmcw)
* Will White (willwhite)
* Konstantin Kaefer (kkaefer)
* Justin Miller (incanus)
