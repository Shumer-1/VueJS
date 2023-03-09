<script setup>
    import {reactive, ref, watchEffect} from "vue"; 

    const counter = ref(0);
    const date = ref(new Date().toLocaleTimeString());

    function counterHandler(event){
        console.log();
    }


    watchEffect(() => {
        setInterval(() => {
            date.value = new Date().toLocaleTimeString();
        }, 1000)
    });
</script>

<template>
        <button @click="counter++">counter {{ counter }}</button>
        <h1>{{ date }}</h1>
</template>



<style lang="scss" scoped>

</style>