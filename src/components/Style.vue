<script setup>
import { ref } from 'vue';


const array = ["red", "bold"];

const red = ref(false);
const bold = ref(false);

function toggleRed() {
    red.value = !red.value;  
}

function toggleBold() {
    bold.value = !bold.value;
}

const style1 = {
    color: "red"
}

const style2 = {
    textTransform: "uppercase",
    fontWeight: "bold"
    // javascript hanya mengenali camel case
    // jadi tidak bisa text-transform, dsb
    // maka dari itu pakai textTransform
}

</script>

<template>
    <h1 :class="{red:red, bold:bold}">contoh text class</h1>
    <!-- <h1 :class="['red','bold']">Style</h1> -->
    <h1 :class="array">contoh text class</h1>
    <button v-on:click="toggleRed">Red</button>
    <button v-on:click="toggleBold">Bold</button>

    <h1 :style="style1">contoh style1</h1>
    <h1 :style="style2">contoh style2</h1>
    <!-- error -->
    <!-- <h1 :style="style1 style2">contoh style1 & style2</h1> -->
    <h1 :style="[style1, style2]">contoh style1 & style2</h1>

</template>

<style scoped>
.red {
    color:red;
}

.bold {
    text-transform: uppercase;
    font-weight: bold;
}
</style>