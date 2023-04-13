<script setup>
 import {ref} from "vue";
 import Header from "./components/Header/Header.vue";

 const isShow = ref(false);
 const text = ref("");

 function a(){
  console.log("Click - take this digit:");
  isShow.value = true;
 };
</script>


<template>
  <Header @myEvent="a"></Header>
  <p v-if="isShow">Надо же, на кнопочку нажал</p>
  <input v-model="text"/>
</template>