<script setup>
    const emit = defineEmits({
        myEvent(event){
            console.log(event);
            if (event.clientX > 30) return true;
            return false;
    },
    });
</script>

<template>
    <div>
        <button @click="$emit('myEvent', $event)">Click</button>
    </div>
</template>