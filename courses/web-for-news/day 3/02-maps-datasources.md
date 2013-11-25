# Map data sources and formats

## Coordinates

#### Geographic latitude and longitude

The latitude (abbreviation: Lat., φ, or phi) of a point on the Earth's surface is the **angle** between the **equatorial plane** and _a line that passes through that point_ and is normal to the surface of a reference ellipsoid which approximates the shape of the Earth.

The Longitude (abbreviation: Long., λ, or lambda) of a point on the Earth's surface is the **angle east or west** from a _reference meridian to another meridian that passes through that point_. 

![Latitude and Longitude of the Earth](http://upload.wikimedia.org/wikipedia/commons/6/62/Latitude_and_Longitude_of_the_Earth.svg)

#### Universal Transverse Mercator coordinate system

Uses a 2-dimensional Cartesian coordinate system to give locations on the surface of the Earth. The **WGS84** ellipsoid is now generally used to model the Earth in the UTM coordinate system

A position on the Earth is given by the UTM zone number and the easting and northing coordinate pair in that zone.

Example: 43°38′33.24″N 79°23′13.7″W is in UTM zone 17, and the grid position is 630084m east, 4833438m north.

![The UTM grid.](http://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Utm-zones.jpg/1280px-Utm-zones.jpg)

* EPSG:4326 refers to WGS84 (treats the earth as an ellipsoid, uses a lat/long coordinate system)
* EPSG:900913 refers to WGS84 Web Mercator (treats the earth as a sphere, uses an x/y axis coordinate system)

Note: 900913 is Google in 1337-speak.

## Map Tiles

Tiles are a way to deliver geographic data in small chunks to a browser or other client app. 

### Raster Tiles

Are square bitmap graphics displayed in a grid arrangement to show a map.

For example [Google Maps: Coordinates, Tile Bounds and Projection](http://www.maptiler.org/google-maps-coordinates-tile-bounds-projection/)

Usage with D3, see [D3 Clipped Map Tiles](http://bl.ocks.org/mbostock/4150951), [D3 Zoomable Map Tiles](http://bl.ocks.org/mbostock/4132797) and another [d3.geo.tile example](http://bl.ocks.org/emeeks/6147081) 

### Vector Tiles

Vector tiles are similar to raster tiles but instead of raster images the data returned is a vector representation of the features in the tile. For example a GeoJSON vector tile might include roads as LineStrings and bodies of water as Polygons.

Check [D3 Vector Tiles](http://bl.ocks.org/mbostock/5593150)

## Shape Files

A shapefile is a digital vector storage format for storing geometric location and associated attribute information. 

A "shapefile" is actually a set of several files, mandatory ones being:

* .shp — shape format; the feature geometry itself
* .shx — shape index format; a positional index of the feature geometry to allow seeking forwards and backwards quickly
* .dbf — attribute format; columnar attributes for each shape, in dBase IV format

## GeoJSON and TopoJSON

**GeoJSON** is an open standard format for encoding collections of simple geographical features along with their non-spatial attributes using JSON (JavaScript Object Notation).

See [GeoJSON Examples](http://en.wikipedia.org/wiki/GeoJSON#Example)

**TopoJSON** is a serialisation format for geographic data that offers efficiency through topological representation. Watch Nelson Minar on [TopoJSON: A Smaller GeoJSON with Some Neat Tricks](http://vimeopro.com/openstreetmapus/state-of-the-map-us-2013/video/68099164)

## GeoTiff

GeoTIFF is a public domain metadata standard which allows georeferencing information to be embedded within a TIFF file. 

The potential additional information includes map projection, coordinate systems and everything else necessary to establish the exact spatial reference for the file. 