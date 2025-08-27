<script setup> // setup wajib
console.info("Hello Vue")

const hello = "<b>Hello Vue</b>"
const helloBro = "<h1>Hello Bro</h1>"
const classHello = "hello"

const id = "hello";

const buttonDisabled = true;

const data = {
    class: "hello",
    id:"hello"
};

function helloFunction() {
    return "Hello Function";
}

</script>

<template>
    <h1 class="hello">Hello Vue</h1>
    <h1 class="hello">{{ hello }}</h1>

    <!-- Kita tidak bisa menggunakan Mustache seperti ini  -->
    <!-- <h1 class="{{classHello}}">{{ hello }}</h1> -->

    <h1 v-bind:class="classHello">{{ hello }}</h1>

    <div v-html="helloBro"></div>

    <div :class="classHello" v-html="helloBro"></div>

    <h1 :id="id" v-bind:class="classHello">{{ hello }}</h1>
    <h1 :id v-bind:class="classHello">{{ hello }}</h1>

    <!-- Boolean Atrribute -->
    <button :disabled="buttonDisabled">This is Button</button>

    <!-- Multiple Attribute -->
    <h1 class="hello">{{ hello }}</h1>

    <!-- Nested Object -->
    <div :class="data.class" v-html="helloBro"></div>

    <!-- JS expression di template -->
    <h1 v-bind="data">{{ hello.toUpperCase() }}</h1>
    <h2>{{ 100 * 200 }}</h2>
    <h2>{{ helloFunction() }}</h2>

</template>

<style scoped>
.hello {
    color: green;
}
</style>