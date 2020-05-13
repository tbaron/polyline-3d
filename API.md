### polyline3d.decode(string[, precision])

Takes a string representation of 1+ 3D coordinate triples
and returns an array of lat, lon, elevation arrays. If not
specified, precision defaults to 5.

### polyline3d.encode(array[, precision])

Takes an array of [lat, lon, elevation] arrays and returns an
encoded string. If not specified, precision defaults to 5.

### polyline3d.fromGeoJSON(geojson[, precision])

Takes a GeoJSON LineString feature and returns an encoded string. If not specified, precision defaults to 5.

### polyline3d.toGeoJSON(string[, precision])

Takes an encoded string and returns a GeoJSON LineString geometry. If not specified, precision defaults to 5.
