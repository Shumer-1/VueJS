<script setup>
 import { Teleport, ref } from "vue";
 import Modal from "./components/Modal/Modal.vue"
 const isShow = ref(false);
</script>

<template>
  <button @click="isShow = !isShow">Показать</button>
  <Modal :show="isShow" @close="isShow = false">Контент модального окна</Modal>
</template>