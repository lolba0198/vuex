<template>
    <p>3. Select in component, array in component</p>
    <select v-model="selected" @change="choose" class="b" @click="click">
        <option v-for="item in array">
            {{ item }}
        </option>
    </select>

    <hr>
</template>

<script>
export default {
    data () {
        return {
            array: [1, 2, 3],
            selected: null
        };
    },

    methods: {
        choose() {
            alert(this.selected)
        }
    }
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

select {
    font-family: 'Roboto', sans-serif;
}
</style>

