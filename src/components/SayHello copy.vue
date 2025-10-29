<script setup>
import { reactive } from 'vue'

const person = reactive({
    firstName: "",
    lastName: ""
})

function sayHello(){
    // tidak perlu person.value.firstName
    // karena balikannya proxy
    person.firstName = document.getElementById("firstName").value;
    person.lastName = document.getElementById("lastname").value;
    
    // jangan menimpa object person yang diatas
    // person = {
    //     firstName: ...
    // }

}
</script>

<template>
    <div>
        <input type="text" placeholder="First Name" id="firstName">
        <br>
        <input type="text" placeholder="Last Name" id="lastname">
        <br>
        <button v-on:click="sayHello">Say Hello</button>
    </div>

    <h1>Hello {{ person.firstName }} {{ person.lastName }}</h1>
</template>

<style scoped>

</style>