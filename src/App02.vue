<template>

<h1>02: Cars</h1>
<div v-for="car in json">
<p>{{ car.car_name }} {{ car.car_type }}</p>
<p>year: {{ car.car_year }}</p>
<img :src="car.image">
<p class="text" :style="{ background: car.hex_color }">kolor auta</p>

<p :style="{ backgroundColor: car.damaged ? 'red' : 'green'}">{{ car.damaged ? 'Uszkodony' : 'Sprawny'}}</p>
<hr>
</div>

</template>

<script>
import JsonData from "./data/cars.json";
export default {
    data() {
        return {
            json: JsonData

        }
    }
}

</script>

<style>
img {
    width: 200px;
}

.text {
    color: rgb(255, 0, 0);
}
</style>