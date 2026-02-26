<template>
  <div style="border: 2px solid green; padding: 10px; margin: 10px;">
    <p><strong>{{ car.car_name }} {{ car.car_type }}</strong></p>
    <img :src="car.image" style="width: 100px;">
    <p>Rok: {{ car.car_year }}</p>
    <button @click="removeCar">USUŃ</button>
  </div>
</template>

<script>
export default {
  props: ['car'],
  methods: {
    removeCar() {
      this.$emit('remove-car', this.car);
    }
  }
}
</script>
