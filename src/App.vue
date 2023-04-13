<script setup>
 import {ref} from "vue";
 import Header from "./components/Header/Header.vue";

 const isShow = ref(false);
 
 function a(number){
  console.log("Click - take this digit:", number);
  isShow.value = true;
 };
</script>


<template>
  <Header @myEvent="a"></Header>
  <p v-if="isShow">Надо же, на кнопочку нажал</p>
</template>