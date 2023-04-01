<script setup>
import { 
    ref} from "vue";
const props = defineProps(["foo", "bar"]);
const time = ref(Date.now());
const timeIntervalid = ref(0);
</script>

<template>
    <div>{{ foo }} {{ bar }}</div>
</template>