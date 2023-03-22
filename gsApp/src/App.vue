<script setup>
import Form from "./components/Form.vue"
import axios from "axios"

const openWeatherMapKey = import.meta.env.VITE_WEATHERMAP_APIKEY

const getCurrentWeatherData = (obj) => {
  axios
  .get(`https://api.openweathermap.org/data/2.5/weather?lat=${obj.latitude}&lon=${obj.longitude}&appid=${openWeatherMapKey}`)
  .then(res => console.log(res))
}

</script>

<template>
  <Form @submit-form="getCurrentWeatherData"/>
</template>
