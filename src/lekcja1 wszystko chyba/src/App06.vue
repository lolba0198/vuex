<template>
  <h1>06: Cars - kup auto (child → parent)</h1>
  
  <SelectYear @year-selected="onYearSelected" />
  

  <div v-if="currentCars.length">
    <h3>Do kupienia:</h3>
    <div v-for="car in currentCars">
      <MyCar2 :car="car" @buy-car="buyCar" />
      <hr>
    </div>
  </div>
  
  <div v-if="boughtCars.length">
    <h3>Kupione auta:</h3>
    <div v-for="car in boughtCars">
      <MyCarKupiony :car="car" @remove-car="removeCar" />
      <hr>
    </div>
  </div>
</template>

<script>
import JsonData from "./data/cars_full.json";
import MyCar2 from "./comps/MyCar2.vue";
import MyCarKupiony from "./comps/MyCarKupiony.vue";
import SelectYear from "./comps/SelectYear.vue";

export default {
  data() {
    return {
      json: JsonData,
      currentCars: [],
      boughtCars: [],
      selectedYear: 2000
    }
  },
  components: { MyCar2, MyCarKupiony, SelectYear },
  methods: {
    onYearSelected(year) {
      this.selectedYear = year;
      this.currentCars = this.json.filter(car => car.car_year === year);
    },
    buyCar(car) {
      this.boughtCars.push(car);
      this.currentCars = this.currentCars.filter(c => c.id !== car.id);
    },
    removeCar(car) {
      this.currentCars.push(car);
      this.boughtCars = this.boughtCars.filter(c => c.id !== car.id);
    }
  }
}
</script>
