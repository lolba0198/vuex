<template>
  <h1>04: Cars - filtrowanie danych</h1>
  <button @click="loadMore">Pokaż więcej</button>
  <div v-for="car in getVisibleCars()">
    <MyCar :car="car"></MyCar>
    <hr>
  </div>
</template>

<script>
import JsonData from "./data/cars_full.json";
import MyCar from "./comps/MyCar.vue";

export default {
  data() {
    return {
      json: JsonData,
      maxId: 5
    }
  },
  components: { MyCar },
  methods: {
    getVisibleCars() {
      return this.json
        .filter(car => car.damaged === true)  
        .slice(0, this.maxId)                 
    },
    loadMore() {
      this.maxId += 5;
    }
  }
}
</script>


<style>
img {
  width: 200px;
}
</style>
