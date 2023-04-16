<script setup>
 import { ref } from "vue";
 import Modal from "./components/Modal/Modal.vue"
 import css from "./App.module.css"
 const isShow = ref(false);
 const isShow2 = ref(false);
</script>

<template>
  <button @click="isShow = true; isShow2=false" :class="css.button">Открыть всплывашку</button>
  <button @click="isShow2 = true; isShow=false" :class="css.button2">Альтернативная кнопка</button>
  <Modal :show="isShow" @close="isShow = false"><b>Всплывашка</b></Modal>
  <Modal :show="isShow2" @close="isShow2=false">Альтернативная версия</Modal>
</template>