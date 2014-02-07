leaflet.TileLayer.WMTS
======================

Add WMTS layering for leaflet

In order to use this plugin, include the leaflet-tilelayer-wmts.js on your page and use it as follow:
```javascript
var matrixIds3857= new Array(22);
for (var i= 0; i<22; i++) {
    matrixIds3857[i]= {
        identifier    : "" + i,
        topLeftCorner : new L.LatLng(20037508,-20037508)
    };
}
var ignKey = "YOUR_KEY";
var layerIGNScanStd = "GEOGRAPHICALGRIDSYSTEMS.MAPS.SCAN-EXPRESS.STANDARD";
var url = "http://wxs.ign.fr/" + ignKey + "/geoportail/wmts";

var ign = new L.TileLayer.WMTS( url ,
                               {
                                   layer: layerIGNScanStd,
                                   style: 'normal',
                                   tilematrixSet: "PM",
                                   matrixIds: matrixIds3857,
                                   format: 'image/jpeg',
                                   attribution: "&copy; <a href='http://www.ign.fr'>IGN</a>"
                               }
                              );
L.control.scale({'position':'bottomleft','metric':true,'imperial':false}).addTo(map);
var baseLayers = {"Carte IGN" : ign};
```
map.addLayer(ign);
