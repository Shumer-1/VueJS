<script setup>
  import { 
    ref,
    reactive,
    watchEffect,
    watch } from "vue";
  import css from "./App.module.css"
  import Cards from "./components/Cards/Cards.vue"

    const cards = ["card_1", "card_2", "card_3"];


</script>

<template>
  <template  v-for="card in cards">
    <Cards>
        <template #slot_1> {{ card }} </template>
        <template #slot_2 > {{ card }} </template>
    </Cards>
  </template>
</template>