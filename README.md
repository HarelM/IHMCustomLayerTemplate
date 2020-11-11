# IHMMapboxMapExample
An example for an external layer for IHM site.
Requirements:
1. geojson source file available online and that is CORS enabled. Can be achived with github and [Githack](https://raw.githack.com/) as can be seen in this repo.
2. `style.json` file that has a `metadata: { "IHM:Overlay": true }` foreach layer. This file is used as the address in the IHM site for a custom layer.
