<script setup>
    import {ref, watchEffect} from "vue"; 

    const counter = ref(0);
    const date = ref(new Date().toLocaleTimeString());
    const counterReverse = ref(100);
    const dateNew = ref(new Date().toDateString());

    watchEffect(() => {
        setInterval(() => {
            date.value = new Date().toLocaleTimeString();
        }, 1000)
    });
    watchEffect(()=>{
        setInterval(()=>{
            dateNew.value = new Date().toDateString();
        }, 1000*60*60*12)
    });

</script>

<template>
        <button @click="counter++">counter {{ counter }}</button>
        <h1>{{ date }}</h1>
        <h2>{{ dateNew }}</h2>
        <button @click="counterReverse--">counterReverse {{ counterReverse }}</button>
</template>



<style lang="scss" scoped>

</style>