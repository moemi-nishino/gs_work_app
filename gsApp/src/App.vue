<script setup>
import axios from "axios"
const openWeatherMapKey = "1e6a0afb89116ed8a742cf296abf1187"
const lat = 35.68202052460928
const lon = 139.76721063068268

const getCurrentWeatherData = () => {
  axios
  .get(`https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lon}&appid=${openWeatherMapKey}`)
  .then(res => console.log(res))
}
</script>

<template>
  <button @click="getCurrentWeatherData">get Current Weather Data test</button>
</template>
