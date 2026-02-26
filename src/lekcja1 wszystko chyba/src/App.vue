<template>
  <h1>01: start Vue + Vite</h1>
  <h2>podział na komponenty, import-export</h2>
  <div id="main">
    <MyButton></MyButton>
    <MyButton2 :prop1="button2Title" :prop2="button2BgColor"></MyButton2>
    <MySelect></MySelect>
    <MySelect2 :prop1="selectArray"></MySelect2>
  </div>
</template>

<script>
import MyButton from "./comps/MyButton.vue";
import MyButton2 from "./comps/MyButton2.vue";
import MySelect from "./comps/MySelect.vue";
import MySelect2 from "./comps/MySelect2.vue";
export default {
  data() {
    return {
    button2Title: "title passed from app",
    button2BgColor: "yellow",
    selectArray: ["red", "green", "blue", "yellow"]
    }
  },
 components: { MyButton, MyButton2, MySelect, MySelect2 }
}
</script>

<style>
#main {
  font-size: 18px;
  font-family: 'Roboto', sans-serif;
  color: blue;
}

h1 {
  color: red;
  font-family: 'Roboto', sans-serif;
}

h2 {
  color: blue;
  font-family: 'Roboto', sans-serif;
}
</style>