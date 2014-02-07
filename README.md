leaflet.TileLayer.WMTS
======================

Add WMTS layering for leaflet

In order to use this plugin, include the leaflet-tilelayer-wmts.js on your page and use it as follow:
```javascript
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
