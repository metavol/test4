<script setup>

import { ref } from 'vue';

const props = defineProps({
    name: String,
    email: String,
})

const emit = defineEmits();

// const username = ref(name);
// const useremail = ref(email);

// defineEmits(['delete']);

const deleting = () => {
    emit("deleting", props.name);
};

const stars = ref('★');
const changeStar = () => {
    stars.value = stars.value + "★";
    if (stars.value.length>5){
        stars.value = '★';
    }
}

</script>

<template>
    <section>
        <h1>{{ stars }}</h1>
        <h2>{{ name }}</h2>
        <h3>{{ email }}</h3>
        <button @click="changeStar" style="margin:0 10px 0 0">Star</button>
        <button @click="deleting">Del</button>

    </section>

</template>

<style>
section{
    border: solid;
    border-color: #777;
    border-radius: 1rem;
    background-color: #444;
    padding: 3rem;
    margin: 1rem;
    transition: background-color 0.5s, border-color 0.5s;
    box-shadow: 3px 3px 3px 0px #666;
}

section:hover{
    background-color: #555;
    border-color: #b44;
}
</style>

