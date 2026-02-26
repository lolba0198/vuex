<template>
  <div>
    <label>Wybierz rok: </label>
    <select v-model="selectedYear" @change="emitYear">
      <option v-for="year in availableYears" :key="year" :value="year">
        {{ year }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedYear: 2000,
      availableYears: []
    }
  },
  mounted() {
    this.availableYears = [1986, 2003, 2004, 2010, 2012, 2020];
  },
  methods: {
    emitYear() {
      this.$emit('year-selected', parseInt(this.selectedYear));
    }
  }
}
</script>
