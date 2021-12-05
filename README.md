# IHM Custom Layer Template

An example for a custom layer for the [IHM site](https://israelhiking.osm.org.il).

Requirements:
1. geojson source file available online and that is CORS enabled. The reference system should be WGS 84.
2. `style.json` file. This file is used to style the layer in the IHM site as a custom layer (either base layer or overlay), and to point to the data source which is the geojson.

If you would like to have different behavior for a base layer or overlay you can use the following tag in the layer `metadata: { "IHM:Overlay": false }` for each layer that you would like to hide when setting this style as an overlay.

CORS enabled can be achieved with GitHub and [Githack](https://raw.githack.com/) as can be seen in this repository.

Walkthrough
===========
1. Creat a geojson file, upload it to GitHub, and create a CORS enabled link using [Githack](https://raw.githack.com/).
2. Create a style.json file with the layer styling that refers to your geojson using the CORS-enabled link. 
3. Upload the style.json to GitHub and create a CORS-enabled link using [Githack](https://raw.githack.com/).
4. In [IHM site](https://israelhiking.osm.org.il), add a new layer and paste the link to the style.json file.



Check out the files in this repository to see how this can be done.
You can use the following address inside IHM site's custom layer control to see a layer with the IHM icon somewhere in the south of israel https://raw.githubusercontent.com/HarelM/IHMMapboxMapExample/main/style.json
Surf to https://israelhiking.osm.org.il/map/9.39/31.6277/35.2993 to see the icon
