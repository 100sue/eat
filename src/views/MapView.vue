<template>
    <div>
  
      <div 
        id="BackBtn" 
        class="absolute z-50 rounded-full bg-white p-1 top-8 left-4"
        
      >
        <ArrowLeftIcon :size="40" />
      </div>
  
      <div id="map" />
  
      <div id="VehicleSelection" class=" w-full">
        <div class="w-full h-2 border-t"></div>
        <div class="w-full text-center border-t-2 p-1.5 text-gray-700 text-lg font-semibold">
          Distance - {{ distance.text }}
        </div>
  
        <div class="scrollSection">
  
          <div class="bg-custom-gray">
            <div class="flex items-center px-4 py-5">
              <img width="75" src="img/uber/ride.png">
              <div class="w-full ml-3">
                <div class="flex items-center justify-between">
                  <div class="text-2xl mb-1">UberX</div>
                  <div class="text-xl">{{  }}</div>
                </div>
                <div class="text-gray-500">{{ duration.text }}</div>
              </div>
            </div>
          </div>
  
          <div>
            <div class="flex items-center px-4 py-5">
              <img width="75" src="img/uber/comfort.png">
              <div class="w-full ml-3">
                <div class="flex items-center justify-between">
                  <div class="text-2xl mb-1">Comfort</div>
                  <div class="text-xl">€{{ }}</div>
                </div>
                <div class="text-gray-500">{{ duration.text }}</div>
              </div>
            </div>
          </div>
  
          <div>
            <div class="flex items-center px-4 py-5">
              <img width="75" src="img/uber/uberxl.png">
              <div class="w-full ml-3">
                <div class="flex items-center justify-between">
                  <div class="text-2xl mb-1">UberXL</div>
                  <div class="text-xl">€{{  }}</div>
                </div>
                <div class="text-gray-500">{{ duration.text }}</div>
              </div>
            </div>
          </div>
  
        </div>
  
        <div 
          class="
            flex 
            items-center 
            justify-center 
            bg-white
            py-6 
            px-4
            w-full 
            absolute 
            bottom-0 
            shadow-inner
          "
        >
          <button 
            class="
              bg-black 
              text-2xl 
              text-white
              py-4 
              px-4 
              rounded-sm
              w-full
            "
          >
            Confirm UberX
          </button>
        </div>
  
      </div>
    </div>
  </template>
  
  <script setup>
 
import { onMounted, ref } from 'vue'
import ArrowLeftIcon from 'vue-material-design-icons/ArrowLeft.vue';
   
  
const distance = ref({text: '', value: null})
const duration = ref({text: '', value: null})
const latLng = ref({ start: { lat: null, lng: null }, end: { lat: null, lng: null } })
  
onMounted(() => {
    setTimeout(() => {
        initMap()
    }, 50)
})
  
const initMap = () => {
    const map = new window.google.maps.Map(document.getElementById("map"), {
    center: {lat:-34.397, lng: 150.644},
    zoom: 8,
    fullscreenControl: false,
    zoomControl: false,
    streetViewControl: false,
    mapTypeControl: false,
    });
    console.log(map)
}
  
</script>
  


<style >
  
#map {
    width:100%;
    height: 45vh;
    top: 0px;
    left: 0px;
}
  
.gm-style-cc {
    display: none;
}
  
    
.scrollSection {
    height: calc(50vh - 120px); 
    position: absolute; 
    overflow-y: auto; 
    width: 100%
}
  
.bg-custom-gray {
    background-color: rgb(237, 237, 237);
}
    
  </style>