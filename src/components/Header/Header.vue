<script setup>
    import {computed} from "vue";
    defineEmits(["myEvent"]);
</script>

<template>
    <div>
        <button @click="$emit('myEvent', $event)"> Click me to see the text </button>
    </div>
</template>