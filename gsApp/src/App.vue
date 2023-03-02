<script setup>
import axios from "axios"

const getWeather = () => {
  axios
  .get("http://api.openweathermap.org/data/2.5/forecast?id=524901&appid=1e6a0afb89116ed8a742cf296abf1187")
  .then(res => console.log(res))
}
</script>

<template>
  <button @click="getWeather">getOpenWeatherAPItest</button>
</template>
