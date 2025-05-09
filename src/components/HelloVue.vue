<script setup> // setup wajib
console.info("Hello Vue")

const hello = "<b>Hello Vue</b>"
const helloBro = "<h1>Hello Bro</h1>"
</script>

<template>
    <h1 class="hello">Hello Vue</h1>
    <h1 class="hello">{{ hello }}</h1>

    <div v-html="helloBro"></div>
</template>

<style scoped>
.hello {
    color: green;
}
</style>