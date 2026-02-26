<template>
  <h1>03: Cars - template in component</h1>
  <div v-for="car in json">
    <MyCar :car="car"></MyCar>
    <hr>
  </div>
</template>

<script>
import JsonData from "./data/cars.json";
import MyCar from "./comps/MyCar.vue";

export default {
  data() {
    return {
      json: JsonData
    }
  },
  components: { MyCar }
}
</script>

<style>
img {
  width: 200px;
}
</style>
