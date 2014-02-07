leaflet.TileLayer.WMTS
======================

Add WMTS layering for leaflet

In order to use this plugin, include the leaflet-tilelayer-wmts.js on your page and use it as follow:
```javascript

// You can get a key here: http://api.ign.fr/accueil (french)
var ignKey = "YOUR_KEY";

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
                                   style: 'normal',
                                   tilematrixSet: "PM",
                                   format: 'image/jpeg',
                                   attribution: "&copy; <a href='http://www.ign.fr'>IGN</a>"
                               }
                              );
L.control.scale({'position':'bottomleft','metric':true,'imperial':false}).addTo(map);

map.addLayer(ign);

var baseLayers = {"Carte IGN" : ign};

L.control.layers(baseLayers, {}).addTo(map);

```

