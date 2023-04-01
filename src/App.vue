<script setup>
  import { 
    ref,
    reactive,
    watchEffect,
    watch } from "vue";
  import css from "./App.module.css"
  import Cards from "./components/Cards/Cards.vue"

    const cards = ["card_1", "card_2", "card_3"];
    const text = ref("");


</script>

<template>
  <input v-model="text"/>
  <template v-for="card in cards">
    <Cards v-if="text === 'show me cards'">
        <template #slot_2>
          <div :class="css.myClass_1" >{{ card }}</div>   
        </template>
        <template #slot_1> {{ card }} </template>
    </Cards>
  </template>
</template>