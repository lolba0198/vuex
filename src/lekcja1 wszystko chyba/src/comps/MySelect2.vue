<template>

<p>4. Select in component, array passed from app</p>

<select v-model="selected" @change="choose" class="b">

<option
v-for="item in prop1"
:style="{ color: item }"
:value="item"
>

{{ item }}

</option>

</select>

<hr>

</template>

<script>

export default {

props: [
"prop1"
],

data() {

return {

selected: null

}

},

methods: {

choose() {

alert(this.selected)

}

}

}

</script>

<style scoped>

.b {

font-size: 30px;
border-radius: 8px;

}

p {

text-decoration: underline;
color: black;

}

select {

font-family: 'Roboto', sans-serif;

}

</style>