# GoogleMapsApi

A class to interact with the google maps api via global callback to init map after successful resolution of the promise.

Allows you to use gmaps properly in with es6 modules


## Usage

Include in your project, and then use like:

```
import GoogleMapsApi from './GoogleMapsApi';

/**
 * MapInit
 * @requires GoogleMapsApi.js
 */
class MapInit {

 constructor() {
   this.gmapApi = new GoogleMapsApi();
   this.mapEl = document.querySelector('.js-map');
 }

 /**
  * Kicks things off on promise to gmaps api
  * @requires _GoogleMapsApi.js
  */
 init() {
   this.gmapApi.load().then(() => {
     this.renderMap(this.data)
   });
 }

 /**
  * Render Map
  * Primary creation of map and markers.
  */
  renderMap(data) {

    // Do map stuffs all like....
    const options = {
      center:      google.maps.LatLng(0, 0),
      mapTypeId:   google.maps.MapTypeId.ROADMAP,
      styles:      stylers.styles,
      zoom:        5,
      scrollwheel: false
    }

    const map = new google.maps.Map(this.mapEl, options);
  }
}

export default MapInit;

// app.js
// import MapInit from './components/MapInit.js';
// let Map = new MapInit();
// Map.init();
```
