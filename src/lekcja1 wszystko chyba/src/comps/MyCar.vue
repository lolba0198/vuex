<template>
  <div>
    <p>{{ car.car_name }} {{ car.car_type }}</p>
    <p>year: {{ car.car_year }}</p>
    <img :src="car.image">
    <p class="text" :style="{ background: car.hex_color }">kolor auta</p>
    <p :style="{ backgroundColor: car.damaged ? 'red' : 'green'}">
      {{ car.damaged ? 'Uszkodony' : 'Sprawny'}}
    </p>
    <button @click="showCarInfo">Pokaż info o aucie</button>
  </div>
</template>

<script>
export default {
  props: ['car'],
  methods: {
    showCarInfo() {
      alert(JSON.stringify(this.car, null, 2));
    }
  }
}
</script>

<style scoped>
.text {
  color: rgb(255, 0, 0);
}
button {
  margin-top: 10px;
  padding: 5px 10px;
}
</style>
