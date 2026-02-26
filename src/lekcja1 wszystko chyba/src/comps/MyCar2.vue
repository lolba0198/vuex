<template>
  <div>
    <p>{{ car.car_name }} {{ car.car_type }} ({{ car.car_year }})</p>
    <p>ID: {{ car.id }}</p>
    <img :src="car.image" style="width: 100px;">
    <p :style="{ backgroundColor: car.damaged ? 'red' : 'green'}">
      {{ car.damaged ? 'Uszkodony' : 'Sprawny'}}
    </p>
    <button @click="buyCar">KUP</button>
  </div>
</template>

<script>
export default {
  props: ['car'],
  methods: {
    buyCar() {
      this.$emit('buy-car', this.car);
    }
  }
}
</script>
