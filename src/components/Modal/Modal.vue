<script setup>
    import { Teleport, Transition } from 'vue';
    import css from "./Modal.module.css";

    defineProps(["show"]);
    defineEmits(["close"]);
</script>

<!---нужно сделать всплывашку
внизу в углу, есть кнопка открыть ее и крестик, 
на фон не влияет-->


<template >
    <Teleport to="#snackbar">
        <Transition>
            <div v-if="show">
                <div :class="css.modal">
                    <div :class="css.modal__header">
                        <button @click="$emit('close')">&times;</button>
                    </div>
                    <div :class="css.modal__body"><slot></slot></div>
                </div>
            </div>
        </Transition>
    </Teleport>
</template>

<style scoped>
.v-enter-active, .v-leave-active{
    transition: opacity 400ms ease;
}
.v-enter-from, .v-leave-to{
    opacity: 0;
}
</style>