<script setup>
</script>

<template>
  <input v-model="text"/>
  <template v-for="card in cards">
    <Cards v-if="text === 'show me cards'">
        <template #slot_2>
          <div :class="css.myClass_1" >{{ card }}</div>   
        </template>
        <template #slot_1> {{ card }} </template>
    </Cards>
  </template>
</template>