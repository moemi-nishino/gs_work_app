<template>
    <form @submit.prevent="submitForm">
        <input type="text" v-model="obj.longitude" placeholder="緯度を入力してください">
        <input type="text" v-model="obj.latitude" placeholder="経度を入力してください">
        <button type="submit">get Current Weather Data</button>

        <div id="map" style="width:100%; height:100%" />
    </form>
</template>

<script setup>
import { reactive } from "vue";

import {Map, View} from "ol";
import TileLayer from "ol/layer/Tile"
import OSM from "ol/source/OSM"
import View from 'ol/View.js';

const map = new Map({
  target: 'map',
  layers: [
    new TileLayer({
      source: new OSM(),
    }),
  ],
  view: new View({
    center: [0, 0],
    zoom: 2,
  }),
});

const obj = reactive({ longitude: "139.76721063068268", latitude: "35.68202052460928" });

const submitForm = () => {
    emits("submit-form", obj)
}

const emits = defineEmits([
    "submit-form"
])


</script>