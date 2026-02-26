<template>
    <p>1. Button in component, style in component</p>
    <button class="b" @click="click">{{ title }}</button>
    <hr>
</template>

<script>
export default {
    data () {
        return {
            title: "button in component",
        };
    },
    methods: {
        click () {
            alert("mega przycisk 1");
        },
    },
};
</script>

<style scoped>
.b {
 font-size: 30px;
 border-radius: 8px;
 background-color: blue;
 color: white;
}

p {
    text-decoration: underline;
    color: black;
}
</style>

