<template>
    <p>2. Button in component, title and bg passed from app</p>

    <button :style="{ background: prop2 }" class="b" @click="click">{{ prop1 }}</button>
    <p>background passed from app: {{ prop2 }}</p>
    <hr>
</template>

<script>
export default {
    props: [
        "prop1",
        "prop2"
    ],
    methods: {
        click () {
            alert("mega przycisk 2");
        },
    },
};
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
</style>