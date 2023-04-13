<script setup>
    defineEmits(["myEvent"]);
</script>

<template>
    <div>
        <button @click="$emit('myEvent', 12)">Click</button>
    </div>
</template>