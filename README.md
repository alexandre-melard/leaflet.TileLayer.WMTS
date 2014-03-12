leaflet.TileLayer.WMTS
======================

Add WMTS layering for leaflet

Demo
http://leaflet.melard.fr


In order to use this plugin, include the leaflet-tilelayer-wmts.js on your page and use it as follow:

```html
<html>
    <head>
        <title>Demo leaflet.TileLayer.WMTS</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width">
        <link rel="stylesheet" href="http://cdn.leafletjs.com/leaflet-0.7.2/leaflet.css" />
        <script src="http://cdn.leafletjs.com/leaflet-0.7.2/leaflet.js"></script>        
        <script src="https://rawgithub.com/mylen/leaflet.TileLayer.WMTS/master/leaflet-tilelayer-wmts.js"></script>
    </head>
    <body>
        <div id="map" style="height: 100%; width: 100%"></div>
        <script>
```
```javascript
// You can get a key here: http://api.ign.fr/accueil (french)
var ignKey = "lqp42l06r6pyp1ll2uuzei4r";

/** Define the layer type
 *  GEOGRAPHICALGRIDSYSTEMS.MAPS
 *  GEOGRAPHICALGRIDSYSTEMS.MAPS.SCAN-EXPRESS.CLASSIQUE
 *  GEOGRAPHICALGRIDSYSTEMS.MAPS.SCAN-EXPRESS.STANDARD
 */
var layerIGNScanStd = "GEOGRAPHICALGRIDSYSTEMS.MAPS.SCAN-EXPRESS.STANDARD";

// The WMTS URL 
var url = "http://wxs.ign.fr/" + ignKey + "/geoportail/wmts";

var ign = new L.TileLayer.WMTS( url ,
                               {
                                   layer: layerIGNScanStd,
                                   style: "normal",
                                   tilematrixSet: "PM",
                                   format: "image/jpeg",
                                   attribution: "<a href='https://github.com/mylen/leaflet.TileLayer.WMTS'>GitHub</a>&copy; <a href='http://www.ign.fr'>IGN</a>"
                               }
                              );
var map = L.map('map').setView([48.505, 3.09], 13);

L.control.scale({'position':'bottomleft','metric':true,'imperial':false}).addTo(map);

map.addLayer(ign);

var baseLayers = {"Carte IGN" : ign};

L.control.layers(baseLayers, {}).addTo(map);            
```
```html
        </script>
    </body>
</html>
```

