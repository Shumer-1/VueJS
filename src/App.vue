<script setup>
  import { ref } from "vue";
  import css from "./App.module.css";

  const text = ref("");
  const cards = ref(["card123", "card289", "card356", "card417", "card505"]);
  const obj = ref([{value_1: 12, value: "first"}, {value_1:22, value: "second"}, {value_1:32, value: "third"}]);
</script>

<template>
  <input type="text" v-model="text"/>
  <template v-for="(card, index) in cards" v-if="text.includes('show')">
    <h1 v-if="card.includes('1') || text === 'show me all'" :class="css.myClassH1">{{ index }}. {{ card }}</h1>
    <div v-for="value in obj">
      <p v-if="value.value_1 === 12" :class="css.myClass_1">{{ value.value }}</p>
      <p v-else-if="value.value_1 === 22" :class="css.myClass_2">{{ value.value }}</p>
      <p v-else :class="css.myClass_3">{{ value.value }}</p>
    </div>
  </template>
  
</template>