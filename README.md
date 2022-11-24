# IHM Custom Layer Template

An example for a custom layer for the [IHM site](https://israelhiking.osm.org.il).

## Some Background
The IHM site uses MapLibre under the hood, this means you need to know a bit about MapLible in order to be able to show a custom layer.
There are many guides available online, I personally like the [examples page](https://maplibre.org/maplibre-gl-js-docs/example/) the most.
The main things to understand is that there are three part to presenting a custom layer in IHM site
1. You need a data source
2. You need to style it using MapLibre rules
3. You need to add a layer to the IHM site using the IHM interface

## Data Srouce
There are 3 main option to choose for the data source:
1. Using the IHM available sources, these can be seen seen in the IHM styles, for example you can see it in the [Hiking Style](https://github.com/IsraelHikingMap/VectorMap/blob/691a0613154a56c9d195c110528212861e22d247/Styles/IHM.json#LL9C10-L9C10)
2. Use overpass turbo query
3. Generate a geojson file and store it

## Examples and Info
The content of the files was not copy paseted here, so you'll need to read this carefully to get it working... :-)

### IHM Source
This is the most simple use case.
The following example uses the IHM data source to show accesible routes:
https://github.com/HarelM/IHMAccessibleRoutes/tree/main
This mean there's only a style.json that uses the IHM source and all you need to do is style it the way you want, you can have a look at the IHM style to understand how to get the data from the relevant layer.

### Overpass turbo source
When the data is not available in the IHM data source, and is available in OSM (might also be zoom related) you can use the overpass to get the data.
The following is an exmaple of a style.json that uses the overpass turbo source
https://gist.githubusercontent.com/zstadler/c9ce8dc115c955fde99eb6b135e0d8fe/raw/30b4396054dd82deb2f1020502db15487819e9a1/Overpass-overlay-example.json
The steps to following is:
1. Go to [Overpass Turbo](https://overpass-turbo.eu/) and create the query you would like to get the data for. Here is an example of a query: https://overpass-turbo.eu/s/1nyV
2. If the query is OK and you see the relevant resutls take the query text (`nw ...` in the above case) to https://www.urlencoder.org/ and encode it,
3. Using the encoded query add it to the `data` field of a geojson source in the publicly availbale style.json file

### Geojson source
The following example uses a geojson file that is stored and updated in the repositry:
https://github.com/amiad/IHMGeoJSONWaterholes
You need to make sure the geojson source is CORS enabled and uses the WGS 84reference system


## Other Info
If you would like to have different behavior for a base layer or overlay you can use the following tag in the layer `metadata: { "IHM:Overlay": false }` for each layer that you would like to hide when setting this style as an overlay.
CORS enabled can be achieved with GitHub and [Githack](https://raw.githack.com/) as can be seen in this repository.
If you need icons that are not part of the IHM site sprite you can write a full url to an image in the icon field of the layer and the IHM site will show that icon.
You can use the following address inside IHM site's custom layer control to see a layer with the IHM icon somewhere in the south of israel https://raw.githubusercontent.com/HarelM/IHMMapboxMapExample/main/style.json
Surf to https://israelhiking.osm.org.il/map/9.39/31.6277/35.2993 to see the icon
