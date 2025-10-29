<script setup>
import { computed, reactive, ref } from 'vue'

const person = reactive({
    firstName: "",
    lastName: ""
})

function sayHello(){
    person.firstName = document.getElementById("firstName").value;
    person.lastName = document.getElementById("lastname").value;
}

// function fullName(){
//     console.log(`fullName called`);
//     return `${person.firstName} ${person.lastName}`; 
// }

// const fullName = computed(() => {
//     console.log(`fullName called`);
//     return `${person.firstName} ${person.lastName}`; 
// })

const fullName = computed((oldName) => {
    console.log(`change old name : ${oldName}`);
    return `${person.firstName} ${person.lastName}`; 
})

const counter = ref(0);

function increment(){
    console.log(`increment called`);
    counter.value++;
}

</script>

<template>
    <div>
        <button v-on:click="increment">increment {{ counter }}</button>
        <br>
        <input type="text" placeholder="First Name" id="firstName">
        <br>
        <input type="text" placeholder="Last Name" id="lastname">
        <br>
        <button v-on:click="sayHello">Say Hello</button>
    </div>

    <!-- <h1>Hello {{ fullName() }}</h1> -->
    <h1>Hello {{ fullName }}</h1>

</template>

<style scoped>

</style>