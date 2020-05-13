# polyline-3d

A simple [google-esque polyline](https://developers.google.com/maps/documentation/utilities/polylinealgorithm)
implementation in Javascript. Compatible with nodejs (`npm install @tbaron/polyline-3d` and the browser (copy `src/polyline3d.js`)).

Encodes/decodes into [lat, lng] coordinate pairs. Use `fromGeoJSON()` to encode from GeoJSON objects, or `toGeoJSON` to
decode to a GeoJSON LineString.

## Installation

    npm install @tbaron/polyline-3d

## Example

```js
var polyline3d = require("@tbaron/polyline");

// returns an array of lat, lon, elevation triplets
polyline3d.decode("_p~iF~ps|U_ulLnnqC_mqNvxq`@");

// returns an array of lat, lon, elevation triplets from polyline6 by passing a precision parameter
polyline3d.decode("cxl_cBqwvnS|Dy@ogFyxmAf`IsnA|CjFzCsHluD_k@hi@ljL", 6);

// returns a GeoJSON LineString feature
polyline3d.toGeoJSON("_p~iF~ps|U_ulLnnqC_mqNvxq`@");

// returns a string-encoded polyline
polyline.encode([
    [38.5, -120.2, 100.1],
    [40.7, -120.95, 101.4],
    [43.252, -126.453, 100.9],
]);

// returns a string-encoded polyline from a GeoJSON LineString
polyline.fromGeoJSON({
    type: "Feature",
    geometry: {
        type: "LineString",
        coordinates: [
            [-120.2, 38.5, 100.1],
            [-120.95, 40.7, 101.4],
            [-126.453, 43.252, 100.9],
        ],
    },
    properties: {},
});
```

[API Documentation](https://github.com/mapbox/polyline/blob/master/API.md)

## Command line

Install globally or run `./node_modules/.bin/polyline3d`.

Send input via stdin and use `--decode`, `--encode`, `--toGeoJSON`, or `--fromGeoJSON` flags. If omitted will default to `--decode`.

Example :

```
cat file.json | ./bin/polyline3d.bin.js --fromGeoJSON > result.txt
```
