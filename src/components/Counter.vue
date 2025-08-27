<script setup>
// kita gunakan let karena datanya bisa berubah
let count = 0;

function increment(){
    console.info(`Increment counter : ${count}`);
    count++;

    document.getElementById('count').innerText = `Counter : ${count}`;
}

</script>

<template>
    <div>
        <h1 id="count">Counter : {{count}}</h1>
        <button v-on:click="increment">Increment</button>
    </div>
</template>

<style scoped>
</style>