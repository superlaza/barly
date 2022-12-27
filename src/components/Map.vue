<!-- <template>
    <div style="height:600px; width:800px">
      <l-map ref="map" :zoom="zoom" :center="[47.41322, -1.219482]">
        <l-tile-layer
          url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
          layer-type="base"
          name="OpenStreetMap"
        ></l-tile-layer>
      </l-map>
    </div>
  </template>
  
  <script>
//   import "leaflet/dist/leaflet.css";
  import { LMap, LTileLayer } from "@vue-leaflet/vue-leaflet";
  
  export default {
    components: {
      LMap,
      LTileLayer,
    },
    data() {
      return {
        zoom: 2,
      };
    },
  };
  </script>
  
  <style></style> -->

<!-- <template>
    <div id="mapContainer">
    </div>
</template>

  <script>
  import "leaflet/dist/leaflet.css";
  import L from "leaflet";
  
  export default {
   name: "Map",
   data() {
     return{
       center: [37,7749, -122,4194]
     }},
   methods: {
     setupLeafletMap: function () {
       const mapDiv = L.map("mapContainer").setView([37,7749, -122,4194], 13);
//        L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
//     maxZoom: 19,
//     attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a>'
// }).addTo(mapDiv);
    //    L.tileLayer(
    //      "http://services.arcgisonline.com/arcgis/rest/services/Canvas/World_Dark_Gray_Base/MapServer/tile/{z}/{y}/{x}",
    //      {
    //     //    attribution:
    //         //  'Map data (c) <a href="https://www.openstreetmap.org/">OpenStreetMap</a> contributors, <a href="https://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery (c) <a href="https://www.mapbox.com/">Mapbox</a>',
    //        maxZoom: 18,
    //     //    id: "mapbox/streets-v11",
    //     //    accessToken:"XXX",
    //      }
    //    ).addTo(mapDiv);
     },
   },
   mounted() {
     this.setupLeafletMap();
   },
  };
  </script>
  
  <style scoped>
  #mapContainer {
   width: 80vw;
   height: 100vh;
  }
  </style> -->