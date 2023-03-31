<script setup>
import { 
    ref,
    reactive,
    onMounted, 
    onBeforeMount, 
    onBeforeUpdate, 
    onUpdated, 
    onBeforeUnmount, 
    onUnmounted } from "vue";
onBeforeMount(() => console.log("beforeMount"));
onMounted(() => console.log("mounted"));
onBeforeUpdate(() => console.log("beforeUpdate"));
onUpdated(() => console.log("updated"));
onBeforeUnmount(() => console.log("beforeUnmount"));
onUnmounted(() => console.log("unmounted"));
</script>

<template>
    <div>1</div>
</template>