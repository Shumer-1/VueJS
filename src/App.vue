<script setup>
  import { 
    ref,
    reactive,
    watchEffect,
    watch } from "vue";
  

  const text = ref("");
  const answer = ref("");
  const answerImg = ref("");


  watch(text, async ()=>{
    console.log("watch");
    if (text.value.indexOf("?") === -1){
      answer.value = "Это не вопрос"; 
      return;
    }
    const res = await fetch("https://yesno.wtf/api");
    const data = await res.json();
    answer.value = data.answer;
    answerImg.value = data.image;
  });

  watchEffect(async ()=>{
    console.log("watchEffect");
    if (text.value.indexOf("?") === -1){
      answer.value = "Это не вопрос"; 
      return;
    }
    const res = await fetch("https://yesno.wtf/api");
    const data = await res.json();
    answer.value = data.answer;
    answerImg.value = data.image;
  });
  function handler(el){
    el.value = Math.random();
  }

</script>

<template>
  <input v-model="text" placeholder="Введите ваш вопрос"/>
  <p v-if="answer">{{ answer }}</p>
  <img v-if="answerImg" :src="answerImg" :alt="answer"/>
  <input v-for="item in 3" :ref="handler"/>
</template>