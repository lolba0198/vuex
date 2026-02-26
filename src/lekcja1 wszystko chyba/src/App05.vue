<template>
  <h1>05: Cars - filtrowanie po roczniku</h1>
  
  <div>
    <label>Rocznik: {{ selectedYear }}</label>
    <input 
      type="range" 
      v-model.number="selectedYear"
      min="1980" 
      max="2025" 
      step="1"
    >
    <span>{{ selectedYear }}</span>
  </div>
  
  <div v-for="car in getCarsByYear()">
    <MyCar :car="car" />
    <hr>
  </div>
  
  <p>Znaleziono samochodów: {{ getCarsByYear().length }}</p>
</template>

<script>
import JsonData from "./data/cars_full.json";
import MyCar from "./comps/MyCar.vue";

export default {
  data() {
    return {
      json: JsonData,
      selectedYear: 2000
    }
  },
  components: { MyCar },
  methods: {
    getCarsByYear() {
      return this.json.filter(car => car.car_year === this.selectedYear);
    }
  }
}
</script>
