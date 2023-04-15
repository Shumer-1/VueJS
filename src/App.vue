<script setup>
 import {ref, Transition} from "vue";
 import Header from "./components/Header/Header.vue";
 import Input from "./components/Input/Input.vue";

 const isShow = ref(false);
 const text = ref("");

 function a(){
  console.log("Click - take this digit:");
  isShow.value = !isShow.value;
 };
</script>


<template>
  <button @click="a">Click me</button><br>
  <Transition mode="out-in">
    <component :is="isShow ? Header: Input"></component>
  </Transition>
</template>

<style>
  .v-enter-active, 
  .v-leave-active{
    transition: all 400ms ease;
  }

  .v-enter-from{
    opacity: 0;
    transform: translateX(-100px);
  }
  .v-leave-to{
    opacity: 0;
    transform: translateX(200px);
  }
</style>