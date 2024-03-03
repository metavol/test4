<script setup>
import {ref} from 'vue';
import HelloWorld from './components/HelloWorld.vue';
import User from './components/User.vue';

const deleteOrdered = (name) => {
  users.value = users.value.filter(u => u.name !== name);
  // console.log(name);
}

const clicked = (e) => {
  users.value.push({
    name: "friend"+(Math.random()*1000).toString().substring(0,3),
    email: "aaa@bbb.ccc"
  })
  console.log(e);
}

const users = ref([]);

users.value.push(

  {
    name:"Taro Uesugi",
    email:"taro@bbb.com"
   },
   {
    name:"Jiro Toyotomi",
    email:"jiro@bbb.com"
   },
   {
    name:"Saburo Sakanoue",
    email:"sab@bbb.com"
   },

);

</script>

<template>
  <!-- <span>
    <HelloWorld msg="Vite + Vue!" />
  </span> -->
  <button @click="clicked">New user</button>
  <div style="display: flex; flex-wrap: wrap;">
    <User v-for="us in users" :name="us.name" :email="us.email" @deleting="deleteOrdered"></User>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.helloworld-container{
  display: flex;
}
</style>
