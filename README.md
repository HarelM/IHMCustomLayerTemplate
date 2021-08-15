# IHMMapboxMapExample

An example for a custom layer for the [IHM site](https://israelhiking.osm.org.il).

Requirements:
1. geojson source file available online and that is CORS enabled. CORS enabled can be achived with github and [Githack](https://raw.githack.com/) as can be seen in this repository.
2. `style.json` file. This file is used in the address of a layer inside the IHM site for a custom layer (either base layer or overlay).

If you would like to have different bevaior for base layer and overlay you can use the following tag in the layer `metadata: { "IHM:Overlay": false }` foreach layer that you would like to hide when setting this style as an overlay.
