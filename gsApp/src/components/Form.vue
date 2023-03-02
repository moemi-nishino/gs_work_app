<template>
    <form @submit.prevent="submitForm">
        <input type="text" v-model="obj.longitude" placeholder="緯度を入力してください">
        <input type="text" v-model="obj.latitude" placeholder="経度を入力してください">
        <button type="submit">get Current Weather Data</button>
    </form>
</template>

<script setup>
import { reactive } from "vue";

const obj = reactive({ longitude: "139.76721063068268", latitude: "35.68202052460928" });

const submitForm = () => {
    emits("submit-form", obj)
}

const emits = defineEmits([
    "submit-form"
])
</script>